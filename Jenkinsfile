pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/yourusername/yourrepo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t my-app .'
            }
        }

        stage('List Images') {
            steps {
                sh 'sudo docker images'
            }
        }

        stage('Tag Image') {
            steps {
                sh 'sudo docker tag my-app my-app:v1'
            }
        }

        stage('Run Container') {
            steps {
                sh 'sudo docker run -d -p 8081:8080 my-app:v1'
            }
        }

        stage('Check Running Containers') {
            steps {
                sh 'sudo docker ps'
            }
        }
    }
}

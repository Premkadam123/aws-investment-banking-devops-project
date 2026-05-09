pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Premkadam123/aws-investment-banking-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t banking-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop banking-container || true'
                sh 'docker rm banking-container || true'
                sh 'docker run -d --name banking-container -p 8081:80 banking-app'
            }
        }

    }
}

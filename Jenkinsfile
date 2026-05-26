pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Nginx Docker') {
            steps {
                sh 'docker rm -f nginx-container || true'
                sh 'docker run -d --name nginx-container -p 8080:80 nginx:latest'
            }
        }
    }
}
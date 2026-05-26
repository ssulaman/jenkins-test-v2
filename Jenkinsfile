pipeline {
    agent any

    stages {
        stage('Run Nginx') {
            steps {
                sh 'docker rm -f nginx-container || true'
                sh 'docker run -d --name nginx-container -p 8080:80 nginx:alpine'
            }
        }
    }
}
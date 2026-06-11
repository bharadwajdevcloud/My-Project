pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite:v1 .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker stop mywebsite-container || true'
                sh 'docker rm mywebsite-container || true'
                sh 'docker run -d -p 8081:80 --name mywebsite-container mywebsite:v1'
            }
        }
    }
}

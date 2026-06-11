pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t mywebsite:v1 .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'sudo docker stop mywebsite-container || true'
                sh 'sudo docker rm mywebsite-container || true'
                sh 'sudo docker run -d -p 8081:80 --name mywebsite-container mywebsite:v1'
            }
        }
    }
}

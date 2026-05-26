pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/sharanamma123/docker-jenkins-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop mycontainer || true'
                sh 'docker rm mycontainer || true'
                sh 'docker run -d -p 80:80 --name mycontainer myapp'
            }
        }
    }
}

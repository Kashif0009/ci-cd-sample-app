pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/kashif0009/ci-cd-sample-app.git'
            }
        }
        stage('Build Docker') {
            steps {
                sh 'docker build -t sample-app:latest .'
            }
        }
        stage('Run Docker') {
            steps {
                sh 'docker rm -f sample-app-container || true'
                sh 'docker run -d -p 5000:5000 --name sample-app-container sample-app:latest'
            }
        }
    }
}

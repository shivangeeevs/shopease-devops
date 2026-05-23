pipeline {
    agent any

    stages {

        stage('Build Backend Docker Image') {
            steps {
                sh 'docker build -t shopease-backend:v1 ./backend'
            }
        }

        stage('Build Frontend Docker Image') {
            steps {
                sh 'docker build -t shopease-frontend:v1 ./frontend'
            }
        }

        stage('Docker Images Check') {
            steps {
                sh 'docker images'
            }
        }
    }
}

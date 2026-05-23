
pipeline {
    agent any

    environment {
        DOCKERHUB_CREDS = credentials('dockerhub-creds')
    }

    stages {

        stage('Build Backend Docker Image') {
            steps {
                sh 'docker build -t shivangeeevs/shopease-backend:v1 ./backend'
            }
        }

        stage('Build Frontend Docker Image') {
            steps {
                sh 'docker build -t shivangeeevs/shopease-frontend:v1 ./frontend'
            }
        }

        stage('Docker Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDS_PSW | docker login -u $DOCKERHUB_CREDS_USR --password-stdin'
            }
        }

        stage('Push Backend Image') {
            steps {
                sh 'docker push shivangeeevs/shopease-backend:v1'
            }
        }

        stage('Push Frontend Image') {
            steps {
                sh 'docker push shivangeeevs/shopease-frontend:v1'
            }
        }

        stage('Docker Images Check') {
            steps {
                sh 'docker images'
            }
        }
    }
}

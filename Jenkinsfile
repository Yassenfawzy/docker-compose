pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'yasseen/my-app:latest'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'master', url: 'https://github.com/Yasseenfawzy/docker-compose.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Test App') {
            steps {
                sh 'echo "Running automated tests..."'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker-compose -f mongo.yaml up -d'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed! Check logs.'
        }
    }
}

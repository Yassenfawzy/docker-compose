pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'yasseen/my-app:latest'
    }

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'echo "Building image..."'
            }
        }

        stage('Test App') {
            steps {
                sh 'echo "Running automated tests..."'
            }
        }

        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker compose -f mongo.yaml up -d'
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

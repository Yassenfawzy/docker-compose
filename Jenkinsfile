pipeline {
    agent any

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
                sh 'echo "Deploying Mongo container via Docker Compose..."'
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

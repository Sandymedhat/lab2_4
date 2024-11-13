// Jenkinsfile

pipeline {
    agent any  // Run the pipeline on any available agent

    environment {
        // You can set environment variables here
        APP_NAME = 'my-app'
        BUILD_DIR = 'build'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build the application (assuming it's a Node.js app in this example)
                script {
                    echo 'Building the application...'
                    sh 'npm install'  // Install dependencies
                    sh 'npm run build' // Run build command
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests (this example assumes the app uses npm tests)
                script {
                    echo 'Running tests...'
                    sh 'npm test'  // Run the tests
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (example assumes using Docker)
                script {
                    echo 'Deploying the application...'
                    sh 'docker-compose up -d'  // Deploy with Docker
                }
            }
        }
    }

    post {
        always {
            echo 'Cleaning up resources...'
            // Clean up resources or perform tasks that run regardless of success/failure
        }

        success {
            echo 'Pipeline completed successfully!'
            // Notify or take action on success
        }

        failure {
            echo 'Pipeline failed.'
            // Notify or take action on failure
        }
    }
}
v

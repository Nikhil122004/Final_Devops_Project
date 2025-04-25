pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Nikhil122004/Final_Devops_Project.git'
            }
        }

        stage('Build & Deploy with Docker Compose') {
            steps {
                script {
                    echo "Stopping existing containers..."
                    sh 'docker compose down'

                    echo "Rebuilding and starting containers..."
                    sh 'docker compose up --build -d'

                    echo "Deployment completed!"
                }
            }
        }
    }
    post {
        success {
            echo "Pipeline executed successfully!"
        }
        failure {
            echo "Pipeline failed. Check logs for errors."
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Pull Latest Code') {
            steps {
                git 'https://github.com/Nikhil122004/Final_Devops_Project.git'
            }
        }

        stage('Deploy App with Docker Compose') {
            steps {
                sh '''
                echo "🧹 Stopping any running containers..."
                docker compose down

                echo "🚀 Building and starting containers..."
                docker compose up -d --build
                '''
            }
        }
    }

    post {
        success {
            echo "✅ App deployed successfully!"
        }
        failure {
            echo "❌ Deployment failed. Check the logs above."
        }
    }
}

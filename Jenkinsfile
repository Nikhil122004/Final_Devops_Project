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

                echo "🚀 Starting containers..."
                docker compose up -d --build
                '''
            }
        }
    }

    post {
        failure {
            echo '❌ Deployment failed. Check the logs above.'
        }
    }
}

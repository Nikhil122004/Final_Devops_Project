pipeline {
    agent any

    stages {
        stage('Pull Latest Code') {
            steps {
                git 'https://github.com/Nikhil122004/Final_Devops_Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                echo "🐳 Building Docker image..."
                docker build -t static_nginx_site .
                '''
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                echo "🧹 Removing any old container..."
                docker rm -f static_nginx_site || true

                echo "🚀 Starting new container..."
                docker run -d -p 3000:80 --name static_nginx_site static_nginx_site
                '''
            }
        }
    }

    post {
        failure {
            echo '❌ Deployment failed. Check the logs above.'
        }
        success {
            echo '✅ Deployment successful! App should be live on port 3000.'
        }
    }
}

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
                sh '''
                echo "Stopping containers..."
                docker-compose down

                echo "Rebuilding and starting containers..."
                docker-compose up --build -d
                '''
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Nikhil122004/Final_Devops_Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t final_devops_project_image .'
            }
        }

        stage('Deploy using Docker Compose') {
            steps {
                bat '''
                docker-compose down || exit 0
                docker-compose up -d --build
                '''
            }
        }
    }
}

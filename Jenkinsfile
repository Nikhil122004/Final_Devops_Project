pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/Nikhil122004/Final_Devops_Project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t final_devops_project_image .'
            }
        }
        stage('Deploy using Docker Compose') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up -d --build'
            }
        }
    }
}

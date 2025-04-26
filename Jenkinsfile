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
                sh 'docker build -t final_devops_project_image .'
            }
        }

        stage('Deploy using Docker Compose') {
            steps {
                sh '''
                docker-compose down || true
                docker-compose up -d --build
                '''
            }
        }
    }
}

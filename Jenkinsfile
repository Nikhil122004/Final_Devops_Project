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
                script{
                    bat 'docker-compose down || true'
                    bat 'docker-compose pull'
                   bat 'docker-compose up -d'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
    }
}
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
                    sh 'docker-compose down || true'
                    sh 'docker-compose pull'
                    sh 'docker-compose up -d'
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
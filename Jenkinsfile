pipeline {
    agent any

    stages {

        stage('Build Docker Images') {
            steps {
                script {
                    // Build the Spring Boot backend Docker image
                    sh 'docker build -t springboot-backend ./lbg-car-spring-app-starter-main'

                    // Build the React frontend Docker image
                    sh 'docker build -t  react-frontend ./lbg-car-react-starter-main'
                }
            }
        }

        stage('Deploy Containers') {
            steps {
                script {
                    // Start the Docker containers using docker-compose
                    sh 'docker-compose -f docker-compose.yml up -d'
                }
            }
        }

        stage('Clean Up') {
            steps {
                script {
                    // Optionally stop and remove containers
                    sh 'docker-compose down'
                }
            }
        }
    }
}

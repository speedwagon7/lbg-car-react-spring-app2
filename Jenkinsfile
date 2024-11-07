pipeline {
    agent any

    stages {
        stage('Clone Repositories') {
            steps {
                git 'https://github.com/speedwagon7/lbg-car-react-spring-app2.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                script {
                    // Build the Spring Boot backend Docker image
                    sh 'docker build -t lbg-car-spring-app-starter-main ./springboot-backend'

                    // Build the React frontend Docker image
                    sh 'docker build -t lbg-car-react-starter-main ./react-frontend'
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

pipeline {
    agent any
    
    stages {
        stage('Clone Repository from Git') {
            steps {
                // Clone the entire Git repository
                git 'https://github.com/RutvijBhesaniya/ThreeTierApp.git'
            }
        }
        
        stage('Build Docker Images') {
            steps {
                // Build Docker images using Docker Compose
                sh 'docker-compose -f docker-compose.yml build'
            }
        }
        
        stage('Deploy Application') {
            steps {
                // Deploy the application using Docker Compose
                sh 'docker-compose -f docker-compose.yml up -d'
            }
        }
    }
    
    post {
        always {
            // Clean up containers after execution
            sh 'docker-compose -f docker-compose.yml down'
        }
    }
}

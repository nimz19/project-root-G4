pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the main project repository containing the Jenkinsfile and docker-compose.yml
                git url: 'https://github.com/nimz19/project-root-G4.git', branch: 'main'
            }
        }
        stage('Build Docker Images') {
            steps {
                // Ensure Docker Compose uses the docker-compose.yml in the project root directory
                sh 'docker-compose -f docker-compose.yml build'
            }
        }
        stage('Deploy Using Docker Compose') {
            steps {
                // Bring down any existing containers and then start the services
                sh 'docker-compose -f docker-compose.yml down'
                sh 'docker-compose -f docker-compose.yml up -d'
            }
        }
    }
}


pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Pull the latest code from the repositories
                git url: 'https://github.com/amyjuliao/lbg-car-react-starter.git', branch: 'main'
                git url: 'https://github.com/amyjuliao/lbg-car-spring-app-starter.git', branch: 'main'
            }
        }
        stage('Build Docker Images') {
            steps {
                sh 'docker-compose -f /home/project-root-G4/docker-compose.yml build'
            }
        }
        stage('Deploy Using Docker Compose') {
            steps {
                sh 'docker-compose -f /home/project-root-G4/docker-compose.yml down'
                sh 'docker-compose -f /home/project-root-G4/docker-compose.yml up -d'
            }
        }
    }
}



pipeline {
    agent any
    stages {
        stage('Checkout Main Repo') {
            steps {
                // Checkout the main repository that contains Jenkinsfile and docker-compose.yml
                git url: 'https://github.com/nimz19/project-root-G4.git', branch: 'main'
            }
        }
        stage('Build and Deploy with Docker Compose') {
            steps {
                // Build and deploy using docker-compose.yml in the main repository
                sh 'docker-compose -f docker-compose.yml down'
                sh 'docker-compose -f docker-compose.yml up -d --build'
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}


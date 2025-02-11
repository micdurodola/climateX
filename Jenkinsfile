pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }
        
        stage('Build Docker Images') {
            steps {
                sh 'docker-compose build'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'docker-compose up -d'
                sh 'docker exec backend npm test'
                sh 'docker-compose down'
            }
        }

        stage('Push Docker Images') {
            steps {
                sh 'docker tag backend YOUR_DOCKERHUB_USERNAME/backend'
                sh 'docker tag frontend YOUR_DOCKERHUB_USERNAME/frontend'
                sh 'docker push YOUR_DOCKERHUB_USERNAME/backend'
                sh 'docker push YOUR_DOCKERHUB_USERNAME/frontend'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s'
            }
        }
    }
}

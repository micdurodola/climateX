pipeline{
    agent any 
    environment {
        DOCKER_USERNAME= "${env.DOCKER_USERNAME}"
        DOCKER_PASSWORD= "${env.DOCKER_PASSWORD}"
        FRONTEND_IMAGE = "${DOCKER_USERNAME}/climate-frontend:latest"
        BACKEND_IMAGE = "${DOCKER_USERNAME}/climate-backend:latest"
    }
    stages{
        stage('Build Frontend Image..................'){
            steps{
                script{
                    // Docker login
                    sh 'echo "$DOCKER_PASSWORD" | docker login -u "$DOCKER_USERNAME" --password-stdin'
                    sh 'docker build -t $FRONTEND_IMAGE -f frontend/Dockerfile .'
                    sh 'docker push $FRONTEND_IMAGE'
                }
            }
        }

        stage('Build Backend image.........................'){
            steps{
                script{
                    // Docker login
                    sh 'echo $DOCKER_PASSWORD | docker login -u "DOCKER_USERNAME" --password-stdin'
                    sh 'docker build -t $BACKEND_IMAGE -f backend/Dockerfile .'
                    sh 'docker push $BACKEND_IMAGE'
                }
            }
        }


        stage('Build deploy.........................'){
            steps{
                script{
                    // Docker login
                    sh 'echo "YO YO YO I am kidding!"'
               
            }
        }
    }
    }
    }
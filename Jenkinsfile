pipeline{
    ageny any 
    environment {
        DOCKER_USERNAME= credentials('docker-username')
        DOCKER_PASSWORD= credentials('docker-password')
        FRONTEND_IMAGE = "${DOCKER_USERNAME}/climate-frontend:latest"
        BACKEND_IMAGE = "${DOCKER_USERNAME}/climate-backend:latest"
    }
    stages{
        stage('Build Frontend Image..................'){
            steps{
                script{
                    // Docker login
                    sh 'echo $DOCKER_PASSWORD | docker login -u DOCKER_USERNAME --password-stdin'
                    sh 'docker build -t $FRONTEND_IMAGE -f Dockerfile.frontend'
                    sh 'docker push $FRONTEND_IMAGE'
                }
            }
        }

        stage('Build Backend image.........................'){
            steps{
                script{
                    // Docker login
                    sh 'echo $DOCKER_PASSWORD | docker login -u DOCKER_USERNAME --password-stdin'
                    sh 'docker build -t $BACKEND_IMAGE -f Dockerfile.backend'
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
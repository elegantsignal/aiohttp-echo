pipeline {
    agent any
    environment {
        DOCKER_HUB = credentials('DOCKER_HUB')
    }
    stages {
        stage('Building image and Deploy to Docker Hub') {
            steps{
                script {
                    docker.withRegistry('', "$DOCKER_HUB") {
                    def dockerImage = docker.build("$DOCKER_IMAGE:$BUILD_NUMBER")
                    dockerImage.push()
                    }
                }
            }
        }
    }
}

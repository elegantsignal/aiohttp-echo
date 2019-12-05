pipeline {
    agent any
    environment {
        DOCKER_HUB = credentials('DOCKER_HUB')
    }
    stages {
        stage('Building image and Deploy to Docker Hub') {
            steps{
                script {
                    withDockerRegistry([ credentialsId: "4a103414-c8be-4efd-b1f9-21c017c5d437", url: "" ]){
                    def dockerImage = docker.build("$DOCKER_IMAGE:$BUILD_NUMBER")
                    dockerImage.push()
                    }
                }
            }
        }
    }
}

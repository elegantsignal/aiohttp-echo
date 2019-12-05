pipeline {
    agent any
    stages {
        stage('Building image') {
            steps{
                script {
                dockerImage = docker.build "$DOCKER_IMAGE:$BUILD_NUMBER"
                }
            }
        }
    }
}

pipeline {
    agent any
	environment {
		IMAGE_REPO_NAME="jenkins-pipeline-build-demo"
		IMAGE_TAG="latest"
	}
        
    
    stages {

        stage ('Code Checkout') {
            steps {
            checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jubernar1993/myPythonDockerRepo.git']])
            }
        }
       
        stage ('Build docker image') {
            steps {
                script {
                dockerImage = docker.build "${IMAGE_REPO_NAME}: ${IMAGE_TAG}"
                //dockerImage = docker.build registry + ":$BUILD_NUMBER"

                }
            }
        }
	}
}

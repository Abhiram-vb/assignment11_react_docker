pipeline {
    agent any
    environment{
        dockerImage=""
        registry="abhiramvaluebound/jenkinsimage"
        registryCredential = "docker"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'docker', url: 'https://github.com/Abhiram-vb/assignment11_react_docker']]])
            }
        }
        stage("build Docker image"){
            steps{
                script{
                    dockerImage = docker.build registry
                }
            }
        }
        stage("upload Docker image"){
            steps{
                script{
                    docker.withRegistry( '', registryCredential ) {
                    dockerImage.push()
                    }
                }
            }
        }
    }
}

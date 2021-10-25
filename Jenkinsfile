pipeline {
    agent any
    environment{
        dockerImage=""
        registry="abhiramvaluebound/testApp"
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Abhiram-vb/assignment11_react_docker']]])
            }
        }
        stage("build Docker image"){
            steps{
                dockerImage = docker.build registry
            }
        }
    }
}

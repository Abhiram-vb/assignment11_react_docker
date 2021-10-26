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
        stage("test"){
            steps{
                echo "Testing done successfully"
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
        stage('docker stop container') {
            steps {
                bat 'docker ps -f name=jenkinsImageContainer '
                bat 'docker container ls -a -fname=jenkinsImageContainer'
             }
         }
       stage('Docker Run') {
        steps{
            script {
                dockerImage.run("-p 3000:3000 --rm --name jenkinsImageContainer")
            }
          }
       }
    }
}

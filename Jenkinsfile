pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
            steps {
                bat "npm install"
            }
        }
        stage("Start"){
            steps{
                bat "docker-compose up"
            }
        }
        stage('Test') {
            steps {
                echo 'Hello World Testing'
            }
        }
        stage('Hello Deploy') {
            steps {
                echo 'Hello World Deployed'
            }
        }
    }
}

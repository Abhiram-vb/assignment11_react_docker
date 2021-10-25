pipeline {
    agent {
        docker{
            image "node:6-alpine"
            args "-p 3000:3000"
        }
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
            steps {
                sh "npm install"
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

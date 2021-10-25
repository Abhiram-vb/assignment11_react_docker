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
        stage("Deploy"){
            steps{
        docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

            def customImage = docker.build("react_docker")

            /* Push the container to the custom Registry */
            customImage.push()
        }
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

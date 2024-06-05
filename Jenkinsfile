pipeline {
    agent {
        docker {
            image 'lnahuel/test:latest'
            reuseNode true
        }
    }
    stages {
        stage('Clone repository') {
            steps {
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                script {
                    app = docker.build("lnahuel/test")
                }
            }
        }
        stage('Test image') {
            steps {
                echo "hola"
            }
        }
    }
}

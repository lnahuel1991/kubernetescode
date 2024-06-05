pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                script {
                    def app
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

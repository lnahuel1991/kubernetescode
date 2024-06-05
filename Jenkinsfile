pipeline {
    agent any
    stages {
        stage('Install Docker') {
            steps {
                script {
                    // Instalar Docker
                    sh 'sudo curl -fsSL https://get.docker.com -o get-docker.sh'
                    sh 'sudo sh get-docker.sh'
                    sh 'sudo usermod -aG docker jenkins'
                }
            }
        }
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

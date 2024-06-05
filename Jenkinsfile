pipeline {
    agent {
        docker {
            image 'mudit097/sample_nodejs:latest'
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
                    // Aquí no necesitas construir la imagen, ya que el agente Docker proporcionará un contenedor con la imagen especificada
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

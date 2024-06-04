pipeline {
    def app
    agent {
        label "kubeagent"
    }
    stages {
        stage('Clone repository') {
            steps {
                checkout scm
            }
        }
        stage('Build image') {
            steps {
                app = docker.build("lnahuel/test")
            }
        }
        stage('Test image') {
            steps {
                echo "hola"
            }
        }
    }
}

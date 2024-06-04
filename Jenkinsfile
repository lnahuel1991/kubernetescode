node {
    def app
    //stage('Initialize para el funcionamiento de docker'){
    //    def dockerHome = tool 'myDocker'
    //    env.PATH = "${dockerHome}/bin:${env.PATH}"
    //}
    stages {
        stage('Add Jenkins user to Docker group') {
            steps {
                sh 'sudo usermod -aG docker $USER'
    }

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("lnahuel/test")
    }

    stage('Test image') {
  

        app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') {
        
        docker.withRegistry('https://registry.hub.docker.com', 'Dockerhub') {
            app.push("${env.BUILD_NUMBER}")
        }
    }
    
    stage('Trigger ManifestUpdate') {
                echo "triggering updatemanifestjob"
                build job: 'updatemanifest', parameters: [string(name: 'DOCKERTAG', value: env.BUILD_NUMBER)]
        }
}

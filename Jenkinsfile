pipeline {
    agent any
    stages {
        stage('checkouthecode') {
            steps {
              git 'https://github.com/karthik7996/docker-sample-nginx.git'   
            }
        }
        stage('builddockerimage') {
            steps {
              sh "docker --version"
              sh "docker build -t nginxapp:1 ." 
             
            }
        }
        
        stage('creating a container') {
            steps {
              sh "docker --version"
              sh "docker rm -f nginxcontainer"
              sh "docker run -d --name nginxcontainer -p 500:80 nginxapp:1" 
            }
        }
    }
}

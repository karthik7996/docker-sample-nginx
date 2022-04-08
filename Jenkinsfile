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
              sh "docker build -t 3.219.234.74:9000/nginxapp:1 ." 
             
            }
        }
        stage('pushing a image'){
            steps {
                sh " docker login http://3.219.234.74:9000 -u admin -p 1234"
                sh "docker push 3.219.234.74:9000/nginxapp:1"

            }
        }
        stage('creating a container') {
            steps {
              sh "docker --version"
              sh "echo "---------delete all contai----"
              sh "docker ps -q | xargs docker stop -y"
              sh "docker ps -q | xargs docker rm -f"  
              sh "docker run -d --name nginxcontainer -p 80:80 3.219.234.74:9000/nginxapp:1" 
            }
        }
    }
}

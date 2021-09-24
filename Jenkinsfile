pipeline {
    agent any 
    stages {
        stage('Build') {
            steps{
               sh "docker build . -t mtomcatwebapp"
                 }
        
        }
        stage('Tag'){
            steps{
                sh "docker tag mtomcatwebapp nikhilkolambe/jenkinstomcat"
            }
        }
        stage('Push'){
            steps{
                withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerHubPwd')]) {
                sh "docker login -u nikhilkolambe -p ${dockerHubPwd}"
            }
                sh "docker push nikhilkolambe/jenkinstomcat"
            }
        }
        stage('Running Container'){
            steps{
                sh "docker run -p 8181:8080 -d -name my-japp nikhilkolambe/jenkinstomcat"
            }
        }
    }
}



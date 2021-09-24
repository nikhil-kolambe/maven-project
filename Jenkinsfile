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
                sh 'docker login -u nikhilkolambe -p winners@123'
                sh "docker push nikhilkolambe/jenkinstomcat"

            }
        }
    }
}



pipeline {
    agent any 
    stages {
        stage('Build') {
            steps{
                sh "docker build . -t mtomcatwebapp"
                sh "docker tag mtomcatwebapp nikhilkolambe/jenkinstomcat"
                sh 'docker login -u nikhilkolambe -p winners@123'
                sh "docker push nikhilkolambe/jenkinstomcat"
            }
        }
    }
}


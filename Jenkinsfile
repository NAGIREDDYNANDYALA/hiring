pipeline {
    agent any

    stages {
        
        stage('Maven Build') {
            steps {
                sh "mvn clean package"
            }
        }
        
        stage('Docker Build') {
            steps {
                sh "docker build -t nagireddynandyala/hiring:0.0.3 ."
            }
        }
        stage('docker push') {
            steps {
                withCredentials([string(credentialsId: 'docker-hub', variable: 'hubpwd')]) {
                    sh "docker login -u nagireddynandyala -p ${hubpwd}"
                   sh "docker push nagireddynandyala/hiring:0.0.3"
                }
            }
        }
    }
}

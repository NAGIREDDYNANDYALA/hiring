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
                ssh "docker login -u nagireddynandyala -p xxxxx"
                ssh "docker push nagireddynandyala/hiring:0.0.3"
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker build -t rakesh210/loadgenerator:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker push rakesh210/loadgenerator:latest"
                    }
                }
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker build -t rakesh210/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker build -t rakesh210/checkoutservice:latest ."
                    }
                }
            }
        }
    }
}

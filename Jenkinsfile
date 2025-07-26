pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker build -t rakesh210/cartservice:latest -f src/Dockerfile src"
                            }    
                    }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'Docker-server')  {
                        sh "docker build -t rakesh210/cartservice:latest ."
                    }
                }
            }
        }
    }
}

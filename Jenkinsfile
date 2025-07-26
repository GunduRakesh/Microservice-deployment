pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'micro-service-cluster', contextName: '', credentialsId: 'k8_token', namespace: 'webapps', serverUrl: 'https://DC777B4E6A7659F97B12AEF73669D12B.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        stage('Get Kubernetes services') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'micro-service-cluster', contextName: '', credentialsId: 'k8_token', namespace: 'webapps', serverUrl: 'https://DC777B4E6A7659F97B12AEF73669D12B.gr7.ap-south-1.eks.amazonaws.com']]) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}

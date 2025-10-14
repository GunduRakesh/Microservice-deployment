pipeline {
    agent any

    stages {
        stage('Deploy to Kubernetes') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'MY-EKS-CLUSTER', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://0B8EBACD65F9ABFDBE83C593181D8C33.gr7.ap-south-1.eks.amazonaws.com') {
                   kubectl apply -f deployment-service.yml
                }
            }
        }
        stage('Get Kubernetes services') {
            steps {
                 withKubeConfig(caCertificate: '', clusterName: 'MY-EKS-CLUSTER', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://0B8EBACD65F9ABFDBE83C593181D8C33.gr7.ap-south-1.eks.amazonaws.com')  {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}

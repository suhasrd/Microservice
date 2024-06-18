pipeline {
    agent any

    stages {
        stage('deploy to kubernetes') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://B18AB27525F31B43545190B740CED4D5.gr7.us-east-1.eks.amazonaws.com']]) {
                  sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        
         stages {
        stage('Hello') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://B18AB27525F31B43545190B740CED4D5.gr7.us-east-1.eks.amazonaws.com']]) {
                  sh "kubectl get svc -n webapps"
            }
        }
    }
}

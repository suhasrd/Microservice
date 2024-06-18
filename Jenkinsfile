pipeline {
    agent any

    stages {
        stage('deploy to kubernetes') {
            steps {
                withKubeConfig([credentialsId: 'k8-token', serverUrl: 'https://B18AB27525F31B43545190B740CED4D5.gr7.us-east-1.eks.amazonaws.com', contextName: '', clusterName: 'EKS-1', namespace: 'webapps']) {
                    sh "kubectl apply -f deployment-service.yml"
                }
            }
        }
        stage('Hello') {
            steps {
                withKubeConfig([credentialsId: 'k8-token', serverUrl: 'https://B18AB27525F31B43545190B740CED4D5.gr7.us-east-1.eks.amazonaws.com', contextName: '', clusterName: 'EKS-1', namespace: 'webapps']) {
                    sh "kubectl get svc -n webapps"
                }
            }
        }
    }
}


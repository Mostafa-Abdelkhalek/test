pipeline {
    agent any

    stages {
        stage('deploy app') {
            steps {
                script {
                    // Corrected 'kubectl apply' commands and 'minikube service' command
                    sh """
                    cd 'E:/Hands on/python pipline/k8s'
                    kubectl apply -f deployment.yml
                    kubectl apply -f svc.yml
                    minikube service python-app-svc --url &
                    """

                }
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('deploy app') {
            steps {
                script {
                    // Corrected 'kubectl apply' commands and 'minikube service' command
                    sh """
                    kubectl apply -f deployment.yml
                    kubectl apply -f svc.yml
                    start minikube service python-app-svc
                    """


                }
            }
        }
    }
}

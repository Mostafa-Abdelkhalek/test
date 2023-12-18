pipeline {
    agent any

    stages {
        stage('Deploy App') {
            steps {
                script {
                    // Run kubectl apply commands
                    sh """
                    kubectl apply -f deployment.yml
                    kubectl apply -f svc.yml
                    """
                }
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Deploy App') {
            steps {
                script {
                    // Run kubectl apply commands
                    sh """
                    /home/tata/bin/kubectl apply -f deployment.yml
                    /home/tata/bin/kubectl apply -f svc.yml
                    """
                }
            }
        }
    }
}
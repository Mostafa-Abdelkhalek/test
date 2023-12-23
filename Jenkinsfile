pipeline {
    agent {
        label 'slave'
    }

    stages {
        stage('Deploy App') {
            steps {
                script {
                    // Run kubectl apply commands
                    sh """
                    kubectl apply -f deployment.yml 
                    kubectl apply -f svc.yml 
                    """
                    sleep (time: 120, units: "SECONDS")
                }
            }
        }
        stage('sleep untill lb getting ready ') {
            steps {
                script {
                    // Run kubectl apply commands
                    sh """
                    kubectl get svc | grep LoadBalancer
                    kubectl describe svc python-app-svc | grep 'LoadBalancer Ingress'
                    """
                }
            }
        }
    }
}
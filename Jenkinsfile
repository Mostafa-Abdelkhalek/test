pipeline {
    agent {
        label 'slave'
    }
    stages{
        stage('deploy app'){
            steps{
                script{
                    sh """
                    kubectl apply -f deployment.yml
                    kubectl apply -f svc.yml
                    """
                    sleep (time: 120 ,units: "SECONDS")
                    
                }
            }

        }
        stage('sleep until lb getting ready'){
            steps{
                script{
                    sh """
                    kubectl describe svc python-app-svc | grep 'LoadBalancer Ingress'
                    """
                }
            }
        }
    }
}
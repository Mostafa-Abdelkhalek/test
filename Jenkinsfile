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
                    sleep (time: 2 ,units: "MINUTES")
                    
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
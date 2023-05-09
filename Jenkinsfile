pipeline {
    agent any    
        stages {
            stage('Creating deployment') {
                steps { 
                     kubeconfig(caCertificate: '/home/knoldus/.minikube/ca.crt', credentialsId: 'kubernetes', serverUrl: 'https://192.168.49.2:8443') {
              //          sh 'kubectl apply -f service.yml'
                        sh 'kubectl apply -f deployment.yml'
                    }  
                    }
            }
            stage('Creating service') {
                steps { 
                    kubeconfig(caCertificate: '/home/knoldus/.minikube/ca.crt', credentialsId: 'kubernetes', serverUrl: 'https://192.168.49.2:8443') {
                        sh 'kubectl apply -f service.yml'
                        // sh 'kubectl apply -f deployment.yml'
                    }  
                }
            }
        }
}

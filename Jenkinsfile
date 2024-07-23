pipeline{
    agent any
        stages{
            stage("k8s"){
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: '9e568145-6ec5-45d9-b379-eeaa710d457a', namespace: 'default', serverUrl: 'https://1D79443C6D74A2616525D144C49071AB.yl4.eu-west-2.eks.amazonaws.com']]) {
                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl get nodes'
                    sh './kubectl create -f pod.yaml'
                    sh './kubectl get pods'
                    }
                }    
        }
    }
}

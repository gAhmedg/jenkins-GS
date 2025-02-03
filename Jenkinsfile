
pipeline {

environment { 
        imageName = 'algn48/nti-app-python'
        yamlfiles = 'kuberenetes/DeploymentAndServices.yml'
                            

    }

    agent any

     stages {
            stage('Verify Branch') {
            steps {
               
                       echo "$GIT_BRANCH"
                     
                
            }
        
            }
   
        // stage('Build and Push Docker Image') {
        //     steps {
                
        //        script {
        //             buildPushtoHub([ image: "${imageName}:${BUILD_NUMBER}", DockerCredentials: 'DOCKERHUB' ])
        //         } 
        //     }
        // }
    
    
    
    stage('Deploy in kubernetes') {
            steps {                                     
                   

withCredentials([string(credentialsId: 'kubecli', variable: 'token')]) {
   sh 'kubectl get pods --token=$token --server=https://kubernetes.default.svc -n devops-tools '
}
    sh 'kubectl get pods --token=<your-token> --server=<your-server-url> -n <namespace>'

                                  
                 
                 
                 
                 
            
        }
        }
    
    
}



}

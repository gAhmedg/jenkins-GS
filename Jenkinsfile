
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
                   

               
               
               withCredentials([string(credentialsId: 'kubecli', variable: '')]) {
    sh 'kubectl get pod'
}
                                  
                 
                 
                 
                 
            
        }
        }
    
    
}



}

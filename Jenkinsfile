
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
                   

            withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: '', contextName: '', credentialsId: '4', namespace: 'ahmedgomaa', serverUrl: 'https://api.ocp-training.ivolve-test.com:6443']]) {    
               
                 
                 sh 'kubectl apply -f python-app.yml -n ahmedgomaa'
                 
                 
            }
        }
        }
    
    
}



}

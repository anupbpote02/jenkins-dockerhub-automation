pipeline { 
    environment {

        registry = "anupbpote/myimage6" 
        registryCredential = 'dockerhub_id' 
        dockerImage = '' 

    }

    agent any 
    stages { 
        stage('Git Checkout') { 
            steps {

                checkout scm
            }
        } 

        stage('Building our image') { 
            steps { 
                
                    
                   sh 'docker login --username anupbpote --password-stdin @Nup_2499'
                   sh 'dockerImage = docker.build registry + ":$BUILD_NUMBER" '

            

            } 
        }
        stage('Deploy our image') { 
            steps {

              script { 
                    docker.withRegistry( '', registryCredential ) { 
                    dockerImage.push() 

                    }
             } 
            }
        } 
}
}

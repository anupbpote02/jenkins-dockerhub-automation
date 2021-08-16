pipeline { 
    environment {

        registry = "anupbpote/myimage5" 
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
                script {
                    
                    docker login --username anupbpote --pasword_stdin @Nup_2499
                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 

                }

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

pipeline { 
    environment {

        registry = "anupbpote/myimage5" 
        registryCredential = 'dockerhub_id' 
        dockerImage = '' 

    }

    agent any 
    stages { 
        stage('Cloning our Git') { 
            steps {

                git 'https://github.com/Anup02499/jenkins5.git' 
            }
        } 

        stage('Building our image') { 
            steps { 
                script {

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

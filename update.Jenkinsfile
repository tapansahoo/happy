pipeline {
    agent any

    stages {
        stage('Copy Archive') {
         steps {
           copyArtifacts filter: 'prod-platform.properties', fingerprintArtifacts: true, projectName: createimage, selector: lastSuccessful
        }
    }
        stage('Manual Approval') {
             input {
                message "Should we continue?"
                ok "Yes, we should."               
                                
            }
			steps {
                  echo 'Aproved'
            }
            
        }
        stage('Deploy') {
        
       
            steps {
                  echo 'Testing..'
            }
        }
    }
}

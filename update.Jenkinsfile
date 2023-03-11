pipeline {
    agent any

    stages {
        stage('Copy Archive') {
         steps {
           copyArtifacts(filter: 'prod-platform.properties', projectName: 'createimage', selector: specific("${lastSuccessful.number}"))
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

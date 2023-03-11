def runCodeBuild() {
  
      script {
          sh(script: """
         
          export image=\$(cat archive/prod-platform.properties)
		  echo \$image
        """ )
      }
    
  }
pipeline {
    agent any

    stages {
        stage('Copy Archive') {
         steps {
           copyArtifacts(filter: 'prod-platform.properties', projectName: 'createimage')
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
        stage('put artifact') {
        
       
            steps {
                  archiveArtifacts(artifacts: 'prod-platform.properties')
            }
        }
		
		stage('Buils') {
        
       
            steps {
                  runCodeBuild()
            }
        }
    }
}

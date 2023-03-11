def runCodeBuild() {
  
      script {
          sh(script: """         
          export image=\$(cat /var/lib/jenkins/jobs/${env.JOB_BASE_NAME}/builds/${currentBuild.number}/archive/prod-platform.properties)
		  echo \$image
		  ansible-playbook  param/ansible/02-UpdateParam.yml -i param/ansible/inventories/Environment/PRD/  -vvv
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

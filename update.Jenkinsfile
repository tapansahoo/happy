pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
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

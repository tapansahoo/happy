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
            
        }
        stage('Deploy') {
        
       
            steps {
                  echo 'Testing..'
            }
        }
    }
}

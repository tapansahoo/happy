pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                 sh 'ansible-playbook param/ansible/00-CreateParamInfra.yml  -i ansible/inventories/Environment/PRD/ -e  "{ansible_python_interpreter: /usr/bin/python3}"'
            }
        }
    }
}

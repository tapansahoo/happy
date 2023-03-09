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
                 sh 'ansible-playbook test_playbook.yml -e  'ansible_python_interpreter=/use/bin/python3''
            }
        }
    }
}

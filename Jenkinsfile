pipeline {
    agent any

    environment {
        ANSIBLE_CONFIG = "${WORKSPACE}/ansible.cfg"
    }

    stages {
        stage('Deploy') {
            steps {
                sh 'ansible-playbook firstPlaybook.yml --tags deploy'
            }
        }
        stage('Start') {
            steps {
                sh 'ansible-playbook firstPlaybook.yml --tags start'
            }
        }
    }
}

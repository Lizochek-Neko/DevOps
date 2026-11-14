pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {
        stage('Подготовка окружения') {
            steps {
                ansiblePlaybook(
                    playbook: 'firstPlaybook.yml',
                    inventory: 'jenkins_inventory.ini',
                    tags: 'deploy',
                    credentialsId: 'node1-ssh-key'
                )
            }
        }
        stage('Запуск приложений') {
            steps {
                ansiblePlaybook(
                    playbook: 'firstPlaybook.yml',
                    inventory: 'jenkins_inventory.ini',
                    tags: 'start',
                    credentialsId: 'node1-ssh-key'
                )
            }
        }
    }
}

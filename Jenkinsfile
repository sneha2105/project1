pipeline {
    agent any
    
    stages {
        stage('SCM-checkout') {
            steps {
                git branch: 'main', credentialsId: 'git-credential', url: 'https://github.com/sneha2105/project1.git'
            }
        }
        stage('Ansible-deployment') {
            steps {
                ansiblePlaybook become: true, credentialsId: 'ec2-user', disableHostKeyChecking: true, installation: 'ansible', inventory: 'host', playbook: 'playbook.yml'
            }
        }
    }
}

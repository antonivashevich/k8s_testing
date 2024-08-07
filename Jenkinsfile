pipeline {
    agent none
    stages {
        stage('Stage 1 - List and Cat Config') {
            agent { label 'master' }
            steps {
                script {
                    sh 'ls -la'
                    sh 'cat config.yaml'
                    sh '''
                        cd ansible
                        ansible-playbook -vv -i hosts playbook.yml --tags k8spods
                }
            }
        }
        stage('Stage 2 - Cat Deployment') {
            agent { label 'redos' }
            steps {
                script {
                    sh 'cat deployment.yaml'
                }
            }
        }
    }
}

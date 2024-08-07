pipeline {
    agent none
    stages {
        stage('Stage 1 - List and Cat Config') {
            agent { label 'master' }
            steps {
                script {
                    sh 'ls -la'
                    sh 'cat config.yaml'
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

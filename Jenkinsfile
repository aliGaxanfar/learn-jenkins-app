pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18'
                    args '-u 130:130'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    npm config set cache /var/lib/jenkins/workspace/test-pipeline/.npm --global
                    npm ci
                    npm run build
                '''
            }
        }
    }
}

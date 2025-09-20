pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18'   // full Node image, not Alpine
                    reuseNode true
                }
            }
            steps {
                sh '''
                    whoami
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}

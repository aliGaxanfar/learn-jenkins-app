pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    mkdir -p /tmp/.npm
                    npm ci --cache /tmp/.npm --userconfig /tmp/.npmrc
                    npm run build
                    ls -la
                '''
            }
        }
    }
}

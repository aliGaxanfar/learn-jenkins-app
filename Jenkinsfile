pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18'
                    args '-u 130:130'  // match Jenkins UID:GID
                    reuseNode true
                }
            }
            steps {
                sh '''
    
                    id
                    ls -la
                    npm ci
                    npm run build
                '''
            }
        }
    }
}

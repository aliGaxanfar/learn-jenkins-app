agent any

stages {
    stage('Build') {
        agent {
            docker {
                image 'node:18-bullseye'
            }
        }
        steps {
            sh '''
                rm -rf node_modules
                npm ci
                npm run build
            '''
        }
    }
}

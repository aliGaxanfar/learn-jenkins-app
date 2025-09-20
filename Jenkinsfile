agent any

stages {
     stage('Clean and Checkout') {
        steps {
            cleanWs()
            checkout scm
        }
    }
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

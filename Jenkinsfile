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
                ls
                ls -la
                node --version
                npm --version
                
                ## npm ci --verbose
                ## npm run build
                ls -la
                '''
            }
        }
    }
}

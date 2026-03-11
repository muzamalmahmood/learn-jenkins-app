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
                apt update
                apt install iputils-ping -y
                ping -c google.com
                npm ci --verbose
                npm run build
                ls -la
                '''
            }
        }
    }
}

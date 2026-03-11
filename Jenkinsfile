pipeline {
    agent {
        docker {
            image 'node:18-alpine'
            reuseNode true
        }
    }

    stages {

        stage('Build') {
            steps {
                sh '''
                node --version
                npm --version
                npm ci
                npm run build
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                find build
                npm test
                '''
            }
        }

    }

    post {
        always {
            junit 'test-results/junit.xml'
        }
    }
}
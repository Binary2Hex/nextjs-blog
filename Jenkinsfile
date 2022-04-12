pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'echo "Node Test"'
                input 'Get User Input'
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}
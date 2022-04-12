pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
     parameters {
                    choice choices: ['"Qin Yue"', '"Fei Fei"', '"Su Han"'], description: 'user name 1', name: 'USER'
                }
    stages {
        stage('Test') {
            input {
                message 'Which user will use to trigger this build'
                ok "Yes, sir"
                parameters {
                    choice choices: ['"Qin Yue"', '"Fei Fei"', '"Su Han"'], description: 'user name 2', name: 'USERNAME'
                }
            }
            steps {
                sh 'node --version'
                sh 'echo "Node Test"'
                echo "User name 1: ${params.USER}"
                echo "User name 2: ${USERNAME}"
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}
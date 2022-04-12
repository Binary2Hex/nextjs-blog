pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
                sh 'echo "Node Test"'
                input {
                    message "Which user will use to trigger this build"
                    parameters {
                        choice(name: 'USERNAME', choices: ['Qin Yue', 'Fei Fei', 'Su Han'], description: 'user name')
                    }
                }
                echo "User name: ${params.USERNAME}"
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}
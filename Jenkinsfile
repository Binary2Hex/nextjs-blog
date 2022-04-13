pipeline {
    agent {
        docker { image 'node:16.13.1-alpine' }
    }
    parameters {
        choice choices: ['http://datalake.pok.stglabs.ibm.com', 'http://9.110.71.16:21000'], description: 'Target Atlas Server', name: 'ATLASE_SERVER' 
        choice choices: ['Qin Yue', 'Fei Fei', 'Su Han'], description: 'Build User', name: 'USER'
    }
    stages {
        stage('Test') {
            // input {
            //     message 'Which user will use to trigger this build'
            //     ok "Yes, sir"
            //     parameters {
            //         choice choices: ['"Qin Yue"', '"Fei Fei"', '"Su Han"'], description: 'user name 2', name: 'USERNAME'
            //     }
            // }
            steps {
                sh 'node --version'
                sh 'echo "Node Test"'
                // sh "./print.sh ${params.USER}"
                sh 'ls -l'
                sh 'print.sh'
                // echo "User name 1: ${params.USER}"
                // echo "User name 2: ${USERNAME}"
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}
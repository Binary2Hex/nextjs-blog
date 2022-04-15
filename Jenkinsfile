pipeline {
    // agent {
    //     docker { image 'node:16.13.1-alpine' }
    // }
    agent any
    parameters {
        choice choices: ['http://datalake.pok.stglabs.ibm.com', 'http://9.110.71.16:21000'], description: 'Target Atlas Server', name: 'ATLASE_SERVER' 
        choice choices: ['Qin Yue', 'Fei Fei', 'Su Han'], description: 'Build User', name: 'USER'
        string name: 'PROJECT', defaultValue: 'zPerfDatalake', description: 'The project name for docker-compose to build containers'
        choice name: 'PORTIDX', choices: [1, 2, 3], description: 'Port index for build'
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
                // sh 'node --version'
                // sh 'echo "Node Test"'
                // sh "./print.sh ${params.USER}"
                // sh 'ls -l'
                // sh "./print.sh '${params.USER}'"
                // echo "User name 1: ${params.USER}"
                // echo "User name 2: ${USERNAME}"
                sh 'git status'
                sh "export PORTN=${params.PORTIDX}; ./print.sh"
            }
        }
    }
    post {
        always {
            echo 'This will always run'
        }
    }
}

// node {
//     stage('Build') {
//         echo 'Building....'
//     }
//     stage('Test') {
//         echo 'Testing....'
//     }
//     stage('Deploy') {
//         echo 'Deploying....'
//     }
// }
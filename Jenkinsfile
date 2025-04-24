// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Hello world!'
//                 echo "BRANCH_NAME = ${env.BRANCH_NAME}"
//                 echo "GIT_BRANCH  = ${env.GIT_BRANCH}"
                
//             }
//         }

//         stage('version') {
//             steps {
//                 sh 'node --version'
//             }
//         }
//     }
// }


pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

         stage('Deliver for development') {
            when {
                branch 'development'
            }
            steps {
                sh './jenkins/scripts/deliver-for-development.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
        
        stage('Deploy for production') {
            when {
                branch 'production'
            }
            steps {
                sh './jenkins/scripts/deploy-for-production.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Hello world!'
                echo "BRANCH_NAME = ${env.BRANCH_NAME}"
                echo "GIT_BRANCH  = ${env.GIT_BRANCH}"
                
            }
        }

        stage('version') {
            steps {
                sh 'node --version'
            }
        }
    }
}

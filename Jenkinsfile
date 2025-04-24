pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Hello world!'
                echo 'La branche est : ${env.BRANCH_NAME}'
            }
        }

        stage('version') {
            steps {
                sh 'node --version'
            }
        }
    }
}

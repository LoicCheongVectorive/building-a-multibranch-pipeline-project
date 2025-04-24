pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Hello world!'
                echo 'La branche est : ${env.GIT_BRANCH}'
            }
        }

        stage('version') {
            steps {
                sh 'node --version'
            }
        }
    }
}

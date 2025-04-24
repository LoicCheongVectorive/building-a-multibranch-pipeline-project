// pipeline {
//     agent any
//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Hello world!'
//             }
//         }
//     }
// }

pipeline {
    agent { docker { image 'node:22.14.0-alpine3.21' } }
    stages {
        stage('build') {
            steps {
                sh 'node --version'
            }
        }
    }
}

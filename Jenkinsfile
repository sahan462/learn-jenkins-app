pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                agent {
                    docker {
                        image 'node:18-alpine'
                        reuseNode true
                    }
                }
                steps {
                    sh '''
                        ls -la
                        node --version
                        npm --version
                        npm ci
                        npm run build
                    '''
                }
                // Add your build steps here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }
}






// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building...'
//                 // Add your build steps here
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo 'Testing...'
//                 // Add your test steps here
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying...'
//                 // Add your deploy steps here
//             }
//         }
//     }

//     post {
//         always {
//             echo 'This will always run after the stages.'
//         }
//         success {
//             echo 'This will run only if the pipeline succeeds.'
//         }
//         failure {
//             echo 'This will run only if the pipeline fails.'
//         }
//     }
// }
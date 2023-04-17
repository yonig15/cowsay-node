pipeline {
    agent any
    tools {
        nodejs 'NodeJS'
    }
    stages {
         stage('checkout'){
            steps{
             checkout scm
            }
        }
        stage('install dependencies') {
            steps {
                dir('./code') {
                    sh 'node --version'
                    sh 'ls'
                    sh 'npm install'
                }
            }
        }
       stage('SonarQube Analysis') {
            steps {
                script {
                    withSonarQubeEnv('Configure-SonarQube ') {
                        def scannerHome = tool 'SonarQube'
                            sh """ ${scannerHome}/bin/sonar-scanner \
                            -Dsonar.projectKey=sqp_c13dda121500a317dcbf8375f82486faf8a4df65 \
                            -Dsonar.login=admin \
                            -Dsonar.password=5245 \
                            -Dsonar.sources=/${env.WORKSPACE}/code """

                        } 
                }
            }
        }
    }
    post {
        success {
            echo 'success'
        }
        failure {
            echo 'fail'
        }
    }
}





 // stage('run Start') {
        //     steps {
        //           dir('./code') {
        //               sh 'npm Start'
        //           }
        //         }
        //     }
        // }

// sh 'export PATH="$PATH:/usr/local/bin"'
//  stage('SonarQube Analysis') {
//             steps {
//             withSonarQubeEnv('SonarQube') {
//             sh 'npm install sonarqube-scanner'
//             sh 'node_modules/.bin/sonar-scanner'
//             }
//             }
//         }


//   stage('checkout'){
//             steps{
//              checkout scm
//             }
//         }


//  stage('run start') {
//             steps {
//                 script {
//                     def counter = 0
//                     while (counter < 10) {
//                         dir('./code') {
//                             sh 'npm start'
//                         }
//                         counter++
//                     }
//                 }
//             }
//         }
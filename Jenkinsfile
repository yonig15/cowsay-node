pipeline {
    agent any
    stages {
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
                   def scannerHome = tool 'SonarQube Scanner 4.8.0.2856';
                    withSonarQubeEnv('SonarQube Scanner 4.8.0.2856') {
                        sh "${scannerHome}/bin/sonar-scanner"
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
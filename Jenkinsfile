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

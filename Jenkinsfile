pipeline {
    agent any
    stages {
        stage('install dependencies') {
            steps {
                dir('./code') {
                    sh 'npm install'
                }
            }
        }
        stage('run start') {
            steps {
                sh 'npm start'
            }
        }
    }
}


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
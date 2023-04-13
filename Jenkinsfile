pipeline {
    agent any

    stages {
        stage('checkout'){
            steps{
             checkout scm
            }
        }
        stage('install dependencies'){
            steps{
             sh 'npm ci'
            }
        }
        stage('run test'){
            steps{
             echo 'npm test'
            }
        }
    }
}



//  stage('SonarQube Analysis') {
//             steps {
//             withSonarQubeEnv('SonarQube') {
//             sh 'npm install sonarqube-scanner'
//             sh 'node_modules/.bin/sonar-scanner'
//             }
//             }
//         }
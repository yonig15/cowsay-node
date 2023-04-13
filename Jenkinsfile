pipeline {
    agent any

    stages {
        stage('checkout'){
            steps{
             echo 'checkout'
            }
        }
        stage('install dependencies'){
            steps{
             echo 'install dependencies'
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
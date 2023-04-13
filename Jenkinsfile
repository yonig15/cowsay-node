pipeline {
    agent any

    stages {
        stage('build') {
            steps {
                sh 'docker-compose up'
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
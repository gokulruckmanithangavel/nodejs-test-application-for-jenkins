pipeline {
    agent {
        docker { image "node:18-alpine"}
    }
    stages {
        stage('Checkout code') {
            steps {
               git branch: 'main', url: 'https://github.com/gokulruckmanithangavel/nodejs-test-application-for-jenkins' 
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Start the app') {
            steps {
                sh 'npm start'
            }
        }
    }
}
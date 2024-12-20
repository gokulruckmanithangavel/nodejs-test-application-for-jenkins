pipeline {
    agent {
        docker { image "node"}
    }
    stages {
        stage('Checkout code') {
            steps {
               git branch: 'main', url: 'https://github.com/gokulruckmanithangavel/nodejs-test-application-for-jenkins' 
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'pwd'
                sh 'ls -la'
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

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
                sh 'sudo chown -R $(whoami) ~/.npm'
                sh 'npm install --unsafe-perm'
            }
        }
        stage('Start the app') {
            steps {
                sh 'npm start'
            }
        }
    }
}

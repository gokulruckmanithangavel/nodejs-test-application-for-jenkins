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
                sh '''
                mkdir -p $WORKSPACE/.npm
                npm config --userconfig=/var/lib/jenkins/workspace/test/.npmrc set cache /var/lib/jenkins/workspace/test/.npm
                npm config set cache $WORKSPACE/.npm
                npm install
                '''
            }
        }
        stage('Start the app') {
            steps {
                sh 'npm start'
            }
        }
    }
}

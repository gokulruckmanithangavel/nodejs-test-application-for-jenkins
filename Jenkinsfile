pipeline {
    agent {
        docker { image "node:23-alpine"}
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
                touch $WORKSPACE/.npmrc
                npm config --userconfig=$WORKSPACE/.npmrc set cache $WORKSPACE/.npm
                npm install --userconfig=$WORKSPACE/.npmrc
                '''
            }
        }
    }
}

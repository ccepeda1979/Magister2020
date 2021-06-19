pipeline {
        
        agent {
        
                docker {
                image 'node:10-alpine'
                args '-p 3001:3001'
                }
        
        }
        
        
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                input message: 'Finished Build Files Team CECG 2021 (Click "Proceed" to continue)'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)?'
             
            }
        }
    }
}

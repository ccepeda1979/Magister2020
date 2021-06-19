pipeline {
  agent {
            node {
                label "master"  //change this as per your agent label
            }
        }
    stages {
        stage('Clone Code New') {
            steps {
                input message: 'Finished Clone New Files'
            }
        }

         stage('Review Code') {
            steps {
                sh './jenkins/scripts/sonar.sh'
            }
        }
     
      
        stage('Build') {
            steps {
                input message: 'Finished Build Files Team CECG 2021 (Click "Proceed" to continue)'
            }
        }

        stage('Test Unitary') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }

        stage('Test Funcionally') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
      
        stage('Test Performance') {
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

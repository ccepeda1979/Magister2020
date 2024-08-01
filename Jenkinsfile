pipeline {
  //agent {
  //          node {
  //              label "master"  //change this as per your agent label
  //          }
  //      }
    stages {
        stage('Clone Code New') {
            steps {
                sleep 10
            }
        }

         stage('Review Code') {
            steps {
                sh './jenkins/scripts/test.sh'
              sleep 10
            }
        }
     
      
        stage('Build') {
            steps {
                input message: 'Finished Build Files Team CECG 2021 (Click "Proceed" to continue)'
              sleep 10
            }
        }

        stage('Test Unitary') {
            steps {
                sh './jenkins/scripts/test.sh'
              sleep 10
            }
        }

        stage('Test Funcionally') {
            steps {
                sh './jenkins/scripts/test.sh'
              sleep 10
            }
        }
      
        stage('Test Performance') {
            steps {
                sh './jenkins/scripts/test.sh'
              sleep 10
            }
        }
      
         stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)?'
              sleep 10
             
            }
        }
    }
}

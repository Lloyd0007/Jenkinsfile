pipeline {
  agent any
  stages {
    stage('Build') {
      options {
        skipDefaultCheckout()
      }
      steps {
        echo 'Building the application...'
        echo "PATH = ${PATH}"
        echo "M2_HOME = ${M2_HOME}"
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo 'Testing the application...'
          }
        }

        stage('Integration Test') {
          steps {
            echo 'start integration test '
            timeout(time: 90) {
              echo 'start performance testing after timeout'
            }

          }
        }

        stage('Performance Test') {
          steps {
            echo 'Carryout the q.a test '
          }
        }

      }
    }

    stage('Deploy') {
      when {
        branch 'master'
      }
      steps {
        echo 'Deploying the application....'
      }
    }

  }
  tools {
    maven 'Maven'
  }
}
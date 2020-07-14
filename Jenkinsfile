pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
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
        input(message: 'Deploy?', ok: 'Yes')
      }
    }

  }
}
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing the application...'
        sh 'jenkins/test-all.sh'
        junit 'report//**/target/*.xml'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application....'
      }
    }

  }
}
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
        sh 'make'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing the application...'
        sh 'make check'
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
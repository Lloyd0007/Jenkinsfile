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
  tools {
    maven 'Maven'
  }
}
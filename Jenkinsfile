pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
        echo 'mvn build'
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
  tools {
    maven 'Maven'
  }
}
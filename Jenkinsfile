pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
        echo "PATH = ${PATH}"
        echo "M2_HOME = ${M2_HOME}"
        sh 'jenkins/build.sh'
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
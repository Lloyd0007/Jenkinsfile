pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building the application...'
        sh 'jenkins/build.sh'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing the application...'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying the application....'
      }
    }

  }
  environment {
    maven = 'Maven 3.6.3'
  }
}
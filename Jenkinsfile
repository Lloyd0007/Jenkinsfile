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
  parameters {
    choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
    booleanParam(name: 'executeTest', defaultValue: 'true', description: '')
  }
}
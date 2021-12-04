pipeline {
  agent any
  stages {
    stage('Fluffy Test') {
      steps {
        sh 'sleep 7'
        echo 'success'
      }
    }

    stage('Fluffy Build') {
      steps {
        sh './jenkins/build.sh'
      }
    }

    stage('Fluffy Deploy') {
      steps {
        echo 'placeholder deploy'
      }
    }

  }
}
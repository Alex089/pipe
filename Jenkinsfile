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
        sh './app.sh'
        sh './jenkins/build.sh'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
      }
    }

    stage('Fluffy Deploy') {
      steps {
        echo 'placeholder deploy'
      }
    }

  }
}

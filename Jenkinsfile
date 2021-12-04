pipeline {
  agent any
  stages {
    stage('Fluffy Test') {
      steps {
        sh 'sleep 3'
        echo 'success'
      }
    }

    stage('Fluffy Build') {
      steps {
        sh 'chmod +x app.sh && chmod +x jenkins/build.sh'
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

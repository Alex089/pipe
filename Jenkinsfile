pipeline {
  agent any
  stages {
    stage('Fluffy Test') {
      parallel {
        stage('Fluffy Test') {
          steps {
            sh 'sleep 3'
            echo 'success'
          }
        }

        stage('Test fluffy2') {
          steps {
            sleep 5
          }
        }

      }
    }

    stage('Fluffy Build') {
      steps {
        sh 'chmod +x app.sh && chmod +x jenkins/build.sh'
        sh 'env'
        sh './app.sh'
        sh 'mkdir target'
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
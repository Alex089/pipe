pipeline {
  agent any
  stages {
    stage('Fluffy Build') {
      steps {
        sh 'chmod +x jenkins/build.sh'
      }
    }

    stage('Fluffy input') {
      steps {
        input(message: 'Hi, deploy', ok: 'Yes')
      }
    }

    stage('Fluffy Test') {
      parallel {
        stage('Backend') {
          steps {
            sh './jenkins/test-all.sh'
            junit 'target/surefire-sfsf'
          }
        }

        stage('Frontend') {
          steps {
            sh './jenkins/test-frontend.sh'
          }
        }

        stage('Performance') {
          steps {
            sh './jenkins/test-performance.sh'
          }
        }

        stage('Static') {
          steps {
            sh './jenkins/test-static.sh'
          }
        }

      }
    }

    stage('Fluffy Deploy') {
      steps {
        sh './jenkins/deploy.sh staging'
      }
    }

    stage('Archive') {
      agent any
      steps {
        archiveArtifacts(artifacts: 'target/**/TEST*.xml', fingerprint: true)
        stash(name: 'Buzz Java 7', includes: 'target/**')
        unstash 'Buzz Java 7'
      }
    }

  }
}
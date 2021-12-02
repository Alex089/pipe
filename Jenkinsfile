pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          input {
            message 'proceed?'
            id 'yes'
            parameters {
              string(name: 'PERSON', defaultValue: 'Eric', description: 'name')
            }
          }
          steps {
            sh 'echo "Hello, ${PERSON}, nice to meet you on ${UBUNTU}"'
            sh 'chmod +x app.sh'
            sh './app.sh'
          }
        }

        stage('Add') {
          steps {
            echo 'test it'
          }
        }

      }
    }

  }
  environment {
    foob = 'bar'
  }
  parameters {
    choice(name: 'UBUNTU', choices: ['18.10', '19.04'], description: 'Chose Ubuntu Release')
  }
}
pipeline {
    agent { dockerfile true }
    stages {
        stage('Test') {
            steps {
                sh 'R --version'
                sh 'echo hi'
                sh 'echo change'
            }
        }
    }
}

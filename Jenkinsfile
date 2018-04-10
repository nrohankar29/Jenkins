pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh 'python hello.py > output.txt'
            sh 'cat output.txt'
          }
        }
        stage('Test') {
          steps {
            echo 'hello'
            pwd(tmp: true)
            deleteDir()
          }
        }
      }
    }
  }
  post {
    always {
      deleteDir()

    }

  }
}
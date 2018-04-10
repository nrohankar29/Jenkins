pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                //running some shell commands
                sh 'python hello.py > output.txt'
                sh 'cat output.txt'
            }
        }
    }
    post {
        always{
            deleteDir()
        }
    }
}

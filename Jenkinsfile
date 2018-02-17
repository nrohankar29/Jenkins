pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                //getting some code from github repo
                git branch:'develop', url:'https://github.com/nrohankar29/Jenkins.git'
            }
        }
        stage('Build') {
            steps {
                //running some shell commands
                sh 'python hello.py > output.txt'
                sh 'cat output.txt'
            }
        }
        stage('Publish') {
            steps {
                //publishing artifacts to s3
                s3Upload consoleLogLevel: 'INFO', dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'jenkinsss', excludedFile: '', flatten: false, gzipFiles: true, keepForever: false, managedArtifacts: true, noUploadOnFailure: true, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '**/*.py', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: true], [bucket: 'jenkinsss', excludedFile: '', flatten: false, gzipFiles: true, keepForever: false, managedArtifacts: true, noUploadOnFailure: true, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '**/*.txt', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: true]], pluginFailureResultConstraint: 'FAILURE', profileName: 'Jenkins', userMetadata: []
            }
        }
    }
}

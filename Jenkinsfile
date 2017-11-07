pipeline {
    agent none
    stages {
        stage('pull git') {
            agent { docker 'alpine/git' }
            steps {
                sh 'git pull https://github.com/pppanther/anko-example.git'
            }
     }
        stage('Build&Deploy') {
            agent { docker 'filiosoft/fastlane:latest' }
            steps {
                sh '/usr/bin/env fastlane android deploy'
            }
        }
    }
}

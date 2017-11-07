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
            agent { docker 'dtr.ci-aldi.com/fastlane:2.64.0-alpine3.6' }
            steps {
                sh '/usr/bin/env fastlane android deploy'
            }
        }
    }
}

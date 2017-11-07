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
            agent { docker 'dtr.ci-aldi.com/fastlane:2.64.0-default' }
            steps {
                sh '/usr/bin/env fastlane android deploy'
            }
        }
    }
}

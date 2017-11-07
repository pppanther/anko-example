pipeline {
    agent none
    stages {
        stage('pull git') {
            agent { docker 'alpine/git' }
            steps {
                sh 'git branch: 'master', url: 'https://github.com/pppanther/anko-example.git''
            }
      // Get the App
     }
        stage('Example Build') {
            agent { docker 'dtr.ci-aldi.com/fastlane:2.63.0-alpine3.6.home' }
            steps {
                sh 'fastlane'
            }
        }
        stage('Example Test') {
            agent { docker 'openjdk:8-jre' }
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}

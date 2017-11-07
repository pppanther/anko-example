pipeline {
    agent none
    stages {
        stage('pull git') {
            agent { docker 'alpine/git' }
            steps {
                sh 'git branch: 'master', credentialsId: '2054e2d4-49e5-48eb-a435-1acb4baf6a8d', url: 'https://github.com/pppanther/anko-example.git'
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

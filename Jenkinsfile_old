#!/usr/bin/env groovy
node {
   stage('pull git') { // for display purposes
      // Get some code from a GitHub repository
      git credentialsId: '2054e2d4-49e5-48eb-a435-1acb4baf6a8d', url: 'https://github.com/pppanther/anko-example.git'
      // Get the App
     }
    /* Requires the Docker Pipeline plugin to be installed */
    docker.image('node:dtr.ci-aldi.com/fastlane:2.63.0-alpine3.6.home').inside {
        stage('build with fastlane in container') {
            sh 'fastlane'
        }
    }
}

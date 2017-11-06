#!/usr/bin/env groovy
node {
    /* Requires the Docker Pipeline plugin to be installed */
    docker.image('node:sonarqube').inside {
        stage('static code analysis ') {
            sh 'sonar-scanner'
        }
    }
}

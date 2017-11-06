pipeline {
        agent none 
        stages {
                stage('pull git') { // for display purposes
			agent { label 'linux-jnlp' }
                        steps {
                        git credentialsId: '2054e2d4-49e5-48eb-a435-1acb4baf6a8d', url: 'https://github.com/pppanther/anko-example.git' }
     }
                stage('build with fastlane in container') {
                        agent { docker 'dtr.ci-aldi.com/fastlane:2.63.0-alpine3.6.home'}
			steps { 
				echo 'Building...'
				sh 'fastlane'
			}
       		 }
    }

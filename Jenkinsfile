pipeline {

environment {
    //Use Pipeline Utility Steps plugin to read information from pom.xml into env variables
    mvnHome = tool name: 'mvn122', type: 'maven'
    mvnCli = "${mvnHome}/bin/mvn"
  }
  
  stages {
    stage('Checkout SCM') {
	steps {
        // using the Pipeline Maven plugin we can set maven configuration settings, publish test results, and annotate the Jenkins console
        withMaven(options: [findbugsPublisher(), junitPublisher(ignoreAttachments: false)]) {
          sh 'mvn clean findbugs:findbugs package'
        }
		}
		}
		}
		}

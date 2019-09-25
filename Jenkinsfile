pipeline {

environment {
    //Use Pipeline Utility Steps plugin to read information from pom.xml into env variables
    mvnHome = tool name: 'mvn122', type: 'maven'
    mvnCli = "${mvnHome}/bin/mvn"
  }
  agent any
  stages {
    stage('Checkout SCM') {
	steps {
         
          git credentialsId: 'githu', url: 'https://github.com/imtiyaz12213/PetClinic.git'
	 
	}
	}
    stage('Build') {
	    steps{
		    
			    sh "${mvnCli} clean compile"
		    
	            }
		}
		
	stage('maven package'){
        steps{
             sh "$(mvnCli} package	
              }
            }			  
		
		
     		}
}

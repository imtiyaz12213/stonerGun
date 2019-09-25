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
		    
			    sh "${mvnCli} clean compile "
		    
	            }
		}
		
	stage('maven package'){
        steps{
		
             sh "/bin/mvn package"	
        
		}
            }

    stage('Deploy To Tomcat'){
	    steps{
		
		      deploy adapters: [tomcat9(credentialsId: '13b583ce-0a8e-45f4-aa2d-b50603fdd198', path: '', url: 'http://18.188.40.235:8080')], contextPath: 'webapp', war: '**/*.war'
			  
			  }
			  
			  }
	
		
		
     		}
}

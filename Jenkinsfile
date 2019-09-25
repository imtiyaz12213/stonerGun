node {
    def mvnHome = tool name: 'mvn122', type: 'maven'
    def mvnCli = "${mvnHome}/bin/mvn"
 agent any 
 stages{
     stage('Checkout SCM'){
        git credentialsId: 'githu', url: 'https://github.com/imtiyaz12213/stonerGun.git'
                          }

     stage('maven compile'){
        // def mvnHome = tool name: 'Maven_3.6', type: 'maven'
        // def mvnCli = "${mvnHome}/bin/mvn"
         sh "${mvnCli} clean compile"
                           }
 
         stage('maven package'){
             sh "${mvnCli} package -Dmaven.test.skip=true"
                  }
    
                    stage('Archive atifacts'){
                 archiveArtifacts artifacts: '**/*.war', onlyIfSuccessful: true
        
                   }
    
              stage('Deploy To Tomcat'){
      
              deploy adapters: [tomcat9(credentialsId: '13b583ce-0a8e-45f4-aa2d-b50603fdd198', path: '', url: 'http://18.188.40.235:8080')], contextPath: 'webapp', war: '**/*.war'
        
             }
    
      }
}

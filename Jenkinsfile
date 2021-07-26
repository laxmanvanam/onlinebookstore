pipeline {
    agent any 
    tools {
        maven 'maven'
    }
    stages{
        stage('git clone'){
            
            steps {
                git 'https://github.com/GorigeRaju1234/onlinebookstore.git'
                
            }
        }
        
    stage ('build') {
        
        steps{
            sh '''mvn clean package'''
        }
        
    }  
    stage ('deploy in tomcat'){
        steps{
            deploy adapters: [tomcat8(credentialsId: 'tomcatcreds', path: '', url: 'http://35.154.48.126:8080/')], contextPath: 'online.war', war: '**/*.war'
        }
    }
        
    }   
}

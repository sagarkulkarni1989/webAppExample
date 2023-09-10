pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git 'https://github.com/sagarkulkarni1989/webAppExample.git'
            }
        }
        
        stage ('Build'){
            
            steps{
                
                sh "mvn package"
             
            }
        }
        
        stage('Deploy'){
            
            steps{
                sshagent(['tomcat2']) {
                   
        
                  sh "scp -o StrictHostKeyChecking=no target/*.war ubuntu@172.31.44.220:/opt/tomcat/webapps"
   
                    
                    
               
                }
                
            }
        }
    }
}


node('master') 
{
  stage('continousdownload')
      { 
          git 'https://github.com/shankar444/Jenkinapp.git'
          
      }
  stage('continousbiuld')
       {
           sh label: '', script: 'mvn package'
           
       }    
    stage('continousdeploy')
       {
           sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.6.205:/var/lib/tomcat9/webapps/testapp.war'
           
       }  
    stage('continoustesting')
       {
           git 'https://github.com/shankar444/Testingapp.git'

       }  
    stage('continousdelivery')
       {
          
           sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/scriptedpipeline/webapp/target/webapp.war ubuntu@172.31.2.111:/var/lib/tomcat9/webapps/prodapp.war'
           
       }  
           
    
}



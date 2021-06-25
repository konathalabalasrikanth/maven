node('master')
{
   properties([pipelineTriggers([pollSCM('* * * * *')])])
   stage('ContinuousDownload') 
   {
       git 'https://github.com/intelliqittrainings/maven.git'    
   }
   stage('ContinuousBuilding')
   {
       sh 'mvn clean package'
   }
   stage('ContinuousDeployment')
   {
       sh 'scp /root/.jenkins/workspace/Jenkins_pipeline/webapp/target/webapp.war root@10.0.2.116:/var/lib/tomcat8/webapps/testapp.war'
   }
   
   
   
}

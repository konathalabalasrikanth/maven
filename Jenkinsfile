node('master')
{
   stage('ContinuousDownload') 
   {
       git 'https://github.com/intelliqittrainings/maven.git'    
   }
   stage('ContinuousBuild')
   {
       sh 'mvn clean'
   }
   stage('ContinuousDeployment')
   {
       sh 'scp /root/.jenkins/workspace/ScriptedPipeline1/webapp/target/webapp.war ubuntu@10.0.2.116:/var/lib/tomcat8/webapps/testapp.war'
   }
   stage('ContinuousTesting')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /root/.jenkins/workspace/ScriptedPipeline1/testing.jar'
       
   }
   stage('ContinuousDelivery')
   {
       
      
   }
   
   
   
}

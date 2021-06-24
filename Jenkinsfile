node('master')
{
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
       sh 'scp /root/.jenkins/workspace/pipe_line_pro/webapp/target/webapp.war root@10.0.2.116:/var/lib/tomcat8/webapps/testapp.war'
   }
   stage('ContinuousTesting')
   {
       git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
       sh 'java -jar /root/.jenkins/workspace/pipe_line_pro/testing.jar'
       
   }
   stage('ContinuousDelivery')
   {
       
      
   }
   
   
   
}

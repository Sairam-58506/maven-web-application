node
{
  
  def mavenHome = tool name: "maven3.8.1"
  properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
  stage('CheckoutCode')
  {
   git branch: 'development', credentialsId: '8806318d-29ea-4806-9803-55208a9fc2fb', url: 'https://github.com/Sairam-58506/maven-web-application.git'
  }
  stage('Build CheckoutCode')
  {
     
   sh "${mavenHome}/bin/mvn clean package"
  }
  /*
  stage('ExecuteSonarQubeReport')
  {
   sh "${mavenHome}/bin/mvn sonar:sonar"   
  }
  stage('UploadArtifactIntoNexus')
  {
   sh "${mavenHome}/bin/mvn deploy"      
  }
  stage('DeployAppIntoTomcat')
  {
   sshagent(['60f47ad5-8098-4c60-b5e2-de66b6a08aac'])
   {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.238.153.177:/opt/apache-tomcat-9.0.45/webapps/"
   }
  }
  stage('SendEmailNotification')
  {
   mail bcc: '', body: '''Build Over...


Regards,
sairam,
8341832285.''', cc: 'sairamh.299@gmail.com', from: '', replyTo: '', subject: 'Build Over', to: 'sairamnaidu585@gmail.com'
  }
  */
}

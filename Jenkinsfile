pipeline
{
agent any
 stages
   {
 stage('SCM checkout')
     {
steps
       {
         git 'https://github.com/Atul-devops/maven-project.git'
		 }
           }
	stage('compile source code')
	{
	steps
	{
	withMaven(jdk: 'local_java', maven: 'local_maven') 
    {
	sh 'mvn compile'
	  }
    }
	   }
	stage('test source code')
	 {
	steps
	    {
	withMaven(jdk: 'local_java', maven: 'local_maven') 
          {
	sh 'mvn test'
          }
	
          }
	    }
		stage('create package-artifact')
	 {
	steps
	    {
	withMaven(jdk: 'local_java', maven: 'local_maven') 
          {
	sh 'mvn package'
          }
	
          }
	    }
	stage('deploy on tomcat')
	{
	steps
	{
	sshagent(['deploytmcat']) 
	{
	sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@3.14.72.70:/webapps'
}
    }
 }
   }
}

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
    }
}

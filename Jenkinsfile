pipeline
{
 agent any
   stages
  {
    stage ('Source code checkout')
	{
	steps
	{
	  git 'https://github.com/Atul-devops/maven-project.git'
	  }
	   }
	 stage('compile the code')
	 {
	   steps
	   {
	      withMaven(jdk: 'local_java', maven: 'local_maven') 
		 { 
		   sh 'mvn compile'
		   }
		  }
		 }
		stage('test the code')
		{
		  steps
		  {
		    withMaven(jdk: 'local_java', maven: 'local_maven') 
			{
			  sh 'mvn test'
		    }
			  }
			   }
		 stage('create package artifact')
		 {
		  steps
		  {
		    withMaven(jdk: 'local_java', maven: 'local_maven') 
			{
			  sh 'mvn package'
			  }
			 }
			} 
		}	
	}

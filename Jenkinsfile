pipeline 
{
agent any
environment {
      PATH = "/bin/mvn:$PATH"
  }
  

stages
 {
      stage("get the code from git")
	{
          steps
		{
            	git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
          
          }
      }
      


stage("build the code ")
	{
          	steps
		{
              sh "mvn clean package"
          	}
      }

stage("deploy stage")
{
          steps
		{
            	 deploy adapters: [tomcat9(credentialsId: 'cred', path: '', url: 'http://13.232.247.123:8080')], contextPath: 'BHUPESH', war: '**/*.war'
          	}
 }
 

 }
}

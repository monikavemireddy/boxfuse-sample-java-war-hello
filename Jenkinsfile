pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }


  stages {
      stage("Get the code from GITGIUB")
{
          steps
{
            git branch: 'master', url: 'https://github.com/GREATCODERHYD/boxfuse-sample-java-war-hello.git'
          
          }
      }




      stage("build code"){
          steps{
              sh "mn clean package"
          }
      }
      stage("deploy the code"){
          steps{
             deploy adapters: [tomcat9(credentialsId: 'id111', path: '', url: 'http://52.66.198.188:8080')], contextPath: 'App', war: '**/*.war'
          }
      }
  }
}

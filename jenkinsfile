pipeline{
agent any
  tools{
     maven 'rihanmaven'
  }

stages{
stage('clone Repo')
  {
    steps{
       git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'     
    }
  }
stage('Build Code')
  {
    steps{
       sh 'mvn package'   
    }
  }

stage('Deploy Code')
  {
    steps{
      deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatcredentials', path: '', url: 'http://13.60.5.211:8080/')], contextPath: null, war: '**/*.war'
}
  }
}

  
}

pipeline{
agent any
  tools{
     maven 'mymaven'
  }

stages{
stage('clone Repo')
  {
    steps{
       git 'https://github.com/iam-hemant/jenkinspipelinetomcat.git'     
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
      deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat01', path: '', url: 'http://43.204.115.88:8080/')], contextPath: null, war: '**/*.war'
    }
  }
}

  
}

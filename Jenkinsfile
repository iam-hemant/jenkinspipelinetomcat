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
      deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat01', path: '', url: 'http://52.66.244.240:8080/')], contextPath: null, war: '**/*.war'
    }
  }
}

  
}

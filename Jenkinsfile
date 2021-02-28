pipeline
{
  agent any
  tools
  {
    maven 'Maven'
  }
  stages
  {
    stage('Build')
    {
      steps
      {
        bat 'mvn package'
      }
    }
    
    stage('Deploy')
    {
      steps
      {
         deploy adapters: [tomcat9(credentialsId: '810807ab-5a56-4bab-bf8f-27b5cb28819d', path: '', url: 'http://localhost:8081/')], contextPath: null, onFailure: false, war: '**/*.war'
      }
    }
  } 
}

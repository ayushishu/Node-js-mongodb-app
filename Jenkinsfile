pipeline {
  agent any
  stages 
  {
    stage('Remove old deployment') 
    {
      steps {
        bat 'docker-compose down '
        }
    }       
    stage('Build and deploy update image')
    {
          steps {
            bat 'docker-compose up -d'
          }
    }      

    
  
  } 
}
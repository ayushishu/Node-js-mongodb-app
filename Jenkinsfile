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
    stage('Build and deploy update image')//for local test 
    {
          steps {
            bat 'docker-compose build --no-cache -d '
          }
    }
    stage('Push node-app image to docker hub'){

          steps {
            bat 'docker push ayushishu/nodeapp'
          }
    }


    
  
  } 
}
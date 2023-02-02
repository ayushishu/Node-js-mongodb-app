//jenkines is running on window OS
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
    stage('Build updated image')//for local test 
    {
          steps {
            bat 'docker-compose build --no-cache '
          }
    }
    stage('Localy Deploy the new build')
    {
          steps {
            bat 'docker-compose up -d'
          }
    }
    stage('Push node-app image to docker hub'){

          steps {
            bat 'docker push ayushishu/nodeapp'
          }
    }
//make sure that you are allready login to azur using '$ az login'
    stage('terraform init'){
      
          steps {
            bat 'terraform init'
          }
    }
    stage('terraform apply') {     
          steps {
            bat 'terraform apply'
          }
    }

  } 
}
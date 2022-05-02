pipeline {
  agent any
 
  
  stages {
    stage("verify tooling") {
      steps {
        bat '''
          docker version
          docker info
          docker compose version 
        '''
      }
    }
   
    stage('Start containers') {
      steps {
        bat 'docker-compose -p kafka-cdc up -d'
        bat 'docker-compose ps'
      }
    }
    
  }
}

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
        bat 'docker-compose -f docker-compose-test.yaml -p kafka-cdc up -d'
        bat 'docker-compose ps'
      }
    }
    stage('move required files to container') {
      steps {
        bat 'docker cp '
      }
    }
  }
}

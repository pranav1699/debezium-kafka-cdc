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
        bat 'docker cp etc/kafka-connect-jdbc-10.4.1.jar kafka-cdc-connect-1:kafka/libs '
        bat 'docker cp etc/postgresql-42.3.3.jar kafka-cdc-connect-1:kafka/libs '
      }
    }
  }
}

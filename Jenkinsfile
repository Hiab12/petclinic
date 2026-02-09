pipeline {
  agent any

  stages {
    stage('Build Docker image (Petclinic)') {
      steps {
        sh 'docker build -t petclinic-app:latest .'
      }
    }

    stage('Deploy stack (compose)') {
        steps {
            sh 'docker-compose down || true'
            sh 'docker-compose up -d'
            sh 'docker-compose ps'
        }
    }
  }
}

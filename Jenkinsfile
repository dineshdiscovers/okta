pipeline {
  agent any
  stages {
    stage('Building Front End') {
      parallel {
        stage('Building Front End') {
          steps {
            sh 'cd client && npm install && ng build'
          }
        }
        stage('Building Back end') {
          steps {
            sh 'cd server && ./mvnw package'
          }
        }
      }
    }
    stage('archieve artifacts') {
      steps {
        archiveArtifacts './server/target/*.jar'
        archiveArtifacts './client/dist/*'
      }
    }
    stage('Build Docker') {
      steps {
        sh 'cd shared && docker-compose up -d --build'
      }
    }
  }
}
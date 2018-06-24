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
  }
}
pipeline {
  agent any
  stages {
    stage('Git Repository') {
      steps {
        sh 'ls -ali'
      }
    }
    stage('Build') {
      steps {
        sh '''npm install
npm build'''
      }
    }
  }
}
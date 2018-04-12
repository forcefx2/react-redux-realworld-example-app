pipeline {
  agent {
    node {
      label 'React'
    }
    
  }
  stages {
    stage('Checkout Code') {
      steps {
        checkout scm
      }
    }
    stage('Verify Tools') {
      parallel {
        stage('node') {
          steps {
            sh 'echo $PATH'
          }
        }
        stage('docker') {
          steps {
            sh 'docker -v'
          }
        }
      }
    }
    stage('Build app') {
      steps {
        sh 'echo "Hello World!"'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
    stage('Verify') {
      steps {
        input 'Everything good?'
      }
    }
    stage('Clean') {
      steps {
        sh 'npm prune'
        sh 'rm -rf node_modules'
      }
    }
  }
}
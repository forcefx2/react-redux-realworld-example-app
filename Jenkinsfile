pipeline {
  agent {
    node {
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
            sh 'echo $PATH'
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
        sh 'echo TEST'
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

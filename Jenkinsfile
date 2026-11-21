pipeline {
  agent any
  tools {
    nodejs "nodejs-26"
  }
  stages {
    stage('Version Check') {
      steps {
        sh 'node -v'
        sh 'npm -v'
      }
    }
    stage('Install Dependencies') {
      steps {
        sh 'npm install --no-audit'
      }
    }
  }
}
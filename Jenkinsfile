pipeline {
  agent any
  tools {
    nodejs "nodejs-26"
  }
  stages {
    stage('Version Check') {
      sh '''
        node -v
        npm -v
      '''
    }
    stage('Install Dependencies') {
      sh 'npm install --no-audit'
    }
  }
}
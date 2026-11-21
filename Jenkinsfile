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
    stage('Dependencies Check') {
      parallel {
        stage('NPM Audit') {
          steps {
              sh 'npm audit --audit-level=critical'
              }
          }
        stage('OWASP Dependency Check') {
          steps {
            dependencyCheck additionalArguments: '--scan . --format ALL --out dependency-check-report', odcInstallation: 'dependency-check-13',  nvdCredentialsId: 'OWASP'
                }
          }
      }
    }
  }
}
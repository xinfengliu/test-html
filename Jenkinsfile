pipeline {
  agent {
    docker {
      image '8.10.0-alpine'
    }
    
  }
  stages {
    stage('build') {
      steps {
        sh 'npm --version'
      }
    }
  }
}
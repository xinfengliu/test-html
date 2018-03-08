pipeline {
  agent {
    docker {
      image 'node:8.10.0-alpine'
    }
  }
  environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
  }
  stages {
    stage('build') {
      steps {
        sh 'npm --version'
        sh '''
          echo "Multiline shell steps works too"
          ls -lah
        '''
      }
    }
  }
  post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
            mail to: 'xxx-yyy-10078-zyzrqd@qq.com',
                 subject: "Jenkins Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Run with ${env.BUILD_URL}"
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
  }
}

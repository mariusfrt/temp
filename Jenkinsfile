pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby...'
        sh 'rvm fix-permissions'
        sh '/bin/bash -l -c "rvm install 2.2"'       
      }
    }
  }
  environment {
    label = 'eytest'
  }
}

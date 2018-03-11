pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby1...'
        sh '/bin/bash -l -c "rvm fix-permissions"'
        sh '/bin/bash -l -c "rvm install 2.2"'
      }
    }
  }
}
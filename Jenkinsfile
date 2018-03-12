pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby1...'
        sh '/bin/bash -l -c "sudo rvm install 2.2"'
      }
    }
  }
}
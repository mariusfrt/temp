pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby1...'
        sh 'sudo /bin/bash -l -c "rvm install 2.2"'
      }
    }
  }
}
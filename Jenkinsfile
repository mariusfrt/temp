pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby...'
        sh '/bin/bash -l -c "rvm install 2.2"'
        sh '/bin/bash -l -c "rvm use 2.2 && gem install bundler -v \\\'~> 1.10\\\' --no-ri --no-rdoc"'
      }
    }
  }
  environment {
    label = 'eytest'
  }
}
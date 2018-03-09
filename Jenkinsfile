pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        timestamps()
      }
    }
    stage('Test1') {
      steps {
        timestamps()
        echo 'test1'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploy'
      }
    }
  }
  environment {
    stage = 'build'
  }
}
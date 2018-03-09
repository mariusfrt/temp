pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Started'
      }
    }
    stage('Test1') {
      steps {
        echo 'Test 1 Started'
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
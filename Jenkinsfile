pipeline {
  agent any
  stages {
    stage('Environment') {
      steps {
        echo 'Installing ruby...'
        sh 'sudo /bin/bash -l -c "rvm install 2.2"'
        sh 'sudo /bin/bash -l -c "rvm use 2.2 && gem install bundler -v \'~> 1.10\' --no-ri --no-rdoc"'
      }
    }
    stage('Checkout') {
      steps {
        script {
          checkout([$class: 'GitSCM',
          branches: [[name: "origin/master"]],
          doGenerateSubmoduleConfigurations: false,
          extensions: [[$class: 'CloneOption', noTags: true, shallow: true]],
          submoduleCfg: [],
          userRemoteConfigs: [[credentialsId: 'eyautomation', url: 'https://github.com/trilogy-group/ey-dredd.git', permissions: 'READABLE']]])
        }
        
      }
    }
    stage('Configure') {
      steps {
        echo 'Setting up configuration files...'
        sh 'cp config/database.yml.travis config/database.yml'
        sh 'cp config/redis.yml.travis config/redis.yml'
        sh 'echo "--profile --color" > .rspec'
        echo 'Installing gems...'
        sh '/bin/bash -l -c "rvm use 2.2 && bundle --deployment"'
        sh '/bin/bash -l -c "rvm use 2.2 && RAILS_ENV=test bundle exec rake db:create db:migrate"'
      }
    }
    stage('Test') {
      steps {
        echo 'Executing tests...'
        sh '/bin/bash -l -c "rvm use 2.2 && RAILS_ENV=test bundle exec rspec -cfd"'
      }
    }
  }
}
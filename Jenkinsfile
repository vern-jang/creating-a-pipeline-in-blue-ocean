pipeline {
  agent {
    docker {
      image 'node:16.17.1-alpine3.15'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('build') {
      steps {
        sh '''npm install -g cnpm --registry http://registry.npm.taobao.org
cnpm install'''
      }
    }

    stage('Test') {
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }

  }
  environment {
    CI = 'true'
  }
}
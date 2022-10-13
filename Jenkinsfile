pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        git(url: 'https://github.com/YuriIzbenko/cicd-pipeline.git', branch: 'main', credentialsId: 'YuriIzbenko')
      }
    }

    stage('Application Build') {
      steps {
        sh 'script scripts/build.sh'
      }
    }

    stage('Tests') {
      steps {
        sh 'script scripts/test.sh'
      }
    }

    stage('Docker Image Buld') {
      steps {
        sh 'docker build'
      }
    }

  }
  environment {
    registry = 'yuriizbenko/cicdpeline'
  }
}
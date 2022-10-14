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
        sh 'docker build -t yuriizbenko/cicdpeline:latest .'
      }
    }

    stage('Docker Login') {
      steps {
        sh '''echo $DOCKERHUB_PASSWORD | docker login -u $DOCKERHUB_LOGIN --password-stdin
'''
      }
    }

    stage('Docker Image Push') {
      steps {
        sh 'docker image push yuriizbenko/cicdpeline:latest'
      }
    }

  }
  environment {
    DOCKERHUB_LOGIN = credentials('DOCKERHUB_LOGIN')
    DOCKERHUB_PASSWORD = credentials('DOCKERHUB_PASSWORD')
  }
}
pipeline {
  agent any
  stages {
    stage('') {
      steps {
        git(url: 'https://github.com/YuriIzbenko/cicd-pipeline.git', branch: 'main', credentialsId: 'YuriIzbenko')
      }
    }

  }
  environment {
    registry = 'yuriizbenko/cicdpeline'
  }
}
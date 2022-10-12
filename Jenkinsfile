pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          git checkout main
        }

        git(url: 'https://github.com/YuriIzbenko/cicd-pipeline.git', branch: 'main', credentialsId: 'YuriIzbenko')
      }
    }

    stage('Application Build') {
      steps {
        script {
          echo
        }

      }
    }

    stage('Tests') {
      steps {
        script {
          script scripts/build.sh
        }

      }
    }

  }
  environment {
    registry = 'yuriizbenko/cicdpeline'
  }
}
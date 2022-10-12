pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          git checkout main
        }

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
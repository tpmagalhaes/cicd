pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'go run epamlabs.go'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deployed EPAM!'
      }
    }

  }
}
pipeline {
    agent { docker 'maven:3-alpine' } 
         }
     }
  stages {
    stage('Build') {
      steps {
        sh 'go get -u github.com/jstemmer/go-junit-report'
        sh 'go build .'
      }
    }

    stage('Test') {
      steps {
        sh 'go test -v 2>&1 | go-junit-report > report.xml'
      }
    }

    stage('Deploy') {
      steps {
        echo '''Epam-Labs-2020
Makes me Happy
And a little nervous - lol'''
      }
    }

  }
  post {
    always {
      junit 'report.xml'
    }

  }


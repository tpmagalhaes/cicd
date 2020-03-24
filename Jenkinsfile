#!/usr/bin/env groovy
pipeline {
  agent any

  stages {
    stage("Build") {
      steps {
        sh 'go build .'
      }
    }

    stage("Deploy") {
      steps {
        sh './epamlabs'
        echo "Deploy!"
      }
    }
  }
}

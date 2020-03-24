pipeline {
    agent { docker { image 'golang' } }

    stages {
        stage('Build') {   
            steps {                                           
                // Create our project directory.
                sh 'cd epamlabs/CI/go-epamlabs'
                
                // Build the app.
                sh 'go build'
            }            
        }

        // Each "sh" line (shell command) is a step,
        // so if anything fails, the pipeline stops.
        stage('Test') {
            steps {                                
                // Remove cached test results.
                sh 'go clean -cache'

                // Run Unit Tests.
                sh 'go test ./... -v'                                  
            }
        }           
    }
}   

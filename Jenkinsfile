pipeline {
    agent {
        docker { image 'golang'}
    }

    stages {
        stage('Build'){
            steps{
                sh 'go get -u github.com/jstemmer/go-junit-report'
                sh 'go build .'
            }
        }
        stage('Test'){
            steps{
                sh 'go test -v 2>&1 | go-junit-report > report.xml'
            }
        }
        stage('Deploy'){
            steps{
                echo "Epam-Labs\nMakes me Happy\nAnd a little nervous - lol"
            }
        }
    }
    // Required to view our test results in the UI
    post {
        always {
            junit 'report.xml'
        }
    }
}

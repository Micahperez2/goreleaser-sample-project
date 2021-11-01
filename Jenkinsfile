pipeline {
    agent any
    environment {
        GITHUB_TOKEN = "${GITHUB_TOKEN}"
    }
    stages {
        stage('Module') {
            steps {
                echo 'Create go module...'
                sh 'go mod init'
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                sh 'go build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'go test -v'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Publish...'
                sh 'goreleaser release --rm-dist'
            }
        }
    }
}

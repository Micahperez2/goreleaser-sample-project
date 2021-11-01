pipeline {
    agent any
    environment {
        GITHUB_TOKEN = "${GITHUB_TOKEN}"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'go build hello-world.go'
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

pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh 'go build'
      }
    }

    stage ('Release') {
      environment {
        GITHUB_TOKEN = credentials('github-token')
      }

      steps {
	sh 'git config --global user.name "Ryan Hoofard"'
	sh 'git config --global user.email "rhoofard2000@gmail.com"'
	sh 'push orgin v0.1.0'
	sh 'goreleaser release'
      }
    }
  }
}


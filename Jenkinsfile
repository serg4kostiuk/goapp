pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        sh "whoami && ls -lsa"
        sh "go version"
        sh "go build main.go"
      }
    }
    stage('Test') {
      steps {
        sh "go test"
      }
    }
    stage('Deploy') {
      steps {
        sh "echo 'deploy app on a server'"
      }
    }
  }
post {
  success {
	slackSend "Build Started - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)"
  }
}
}



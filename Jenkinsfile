pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git credentialsId: 'github_token', url: 'https://github.com/umeshtilak91/java-docker-pipeline.git'
      }
    }

    stage('Build Java') {
      steps {
        sh 'chmod +x build.sh'
        sh './build.sh'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t java-hello .'
      }
    }

    stage('Run Docker Image') {
      steps {
        sh 'docker run --rm java-hello'
      }
    }
  }
}

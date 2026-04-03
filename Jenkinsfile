pipeline {
  agent any

  stages {

    stage('Clone Code') {
      steps {
        git 'https://github.com/Jay-vardhan-14/devops-webapp'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t myapp .'
      }
    }

    stage('Run Container') {
      steps {
        sh 'docker stop myapp || true'
        sh 'docker rm myapp || true'
        sh 'docker run -d -p 80:80 --name myapp myapp'
      }
    }

  }
}

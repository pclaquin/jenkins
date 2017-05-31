pipeline {
  agent any
  stages {
    stage('Input') {
      steps {
        echo 'Please input credentials'
      }
    }
    stage('Configuration initiale') {
      steps {
        sh 'bash setup.sh'
      }
    }
  }
}
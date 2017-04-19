pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
      }
    }
    stage('scan') {
      steps {
        sh 'docker run mosheco/my-docker-whale'
      }
    }
  }
}
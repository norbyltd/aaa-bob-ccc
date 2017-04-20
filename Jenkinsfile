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
        sh 'docker run --rm -v /tmp:/tmp aquasec/scanner-cli:2.0 --registry "Docker Hub" -image mongo:latest --host https://train.aquasec.com/ --user scanner --password scanner1234 --show-negligible --htmlfile out.html --jsonfile out.json'
      }
    }
  }
}
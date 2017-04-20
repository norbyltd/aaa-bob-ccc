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
        sh 'docker run --rm -v /tmp:/tmp aquasec/scanner-cli:2.0 --registry "Docker Hub" -image mongo:latest --host https://train.aquasec.com/ --user $USER --password $PASSWORD --show-negligible --htmlfile out.html --jsonfile out.json'
      }
    }
    stage('copy') {
      steps {
        archiveArtifacts '/tmp/out.*'
        sh 'cp /tmp/out.* .'
      }
    }
    stage('archive') {
      steps {
        archiveArtifacts 'out.*'
      }
    }
  }
  environment {
    USER = 'scanner'
    PASSWORD = 'scanner1234'
  }
}
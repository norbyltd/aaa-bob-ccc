stage('Unit Tests') {
  steps {
    parallel
      'Jasmine' {
        sh 'gulp karma-tests-ci'
      },
      'Mocha' {
        sh 'gulp mocha-tests'
      }
  }
  post {
    success {
      junit 'test/coverage/jasmine-results.xml'
      junit 'test/coverage/mocha-results.xml'
    }
  }
}

pipeline {
  agent any
  stages {
    stage('build') {
      steps {
         sh 'echo build'

      }
    }
    stage('test') {
      steps {
         sh '/usr/local/Cellar/phantomjs/2.1.1/bin/phantomjs ./src/test/js/runner.js ./src/test/js/qunit.html'
      }
    }
  }
}

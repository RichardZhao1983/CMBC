pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm config ls'
        sh 'npm install -g grunt-cli'
        sh 'npm install node-rfc@next'
        sh 'npm install grunt --no-color default'   
      }
    }
  }
}

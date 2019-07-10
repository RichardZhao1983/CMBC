pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm config ls'
        sh 'npm install grunt --no-color --gruntfile Gruntfile.js default'   
      }
    }
  }
}

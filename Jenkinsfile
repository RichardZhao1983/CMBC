pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm install -g grunt-cli'
        sh 'npm install node-rfc@next'
        sh 'npm install grunt --no-color --gruntfile Gruntfile.js default'
        sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST'   
      }
    }
  }
}

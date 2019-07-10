pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
        sh 'npm --registry https://registry.npm.taobao.org node-rfc@next'
        sh 'npm install grunt --no-color --gruntfile Gruntfile.js default'
        sh 'npm install grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST'   
      }
    }
  }
}

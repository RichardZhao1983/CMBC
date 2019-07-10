pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
        sh 'npm --registry https://registry.npm.taobao.org install node-rfc@next'
        sh 'npm --registry https://registry.npm.taobao.org install grunt --no-color default'
        sh 'npm install grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST'   
      }
    }
  }
}

pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
        sh 'npm --registry https://npm.sap.com/ install node-rfc@next'
        sh 'npm --registry https://registry.npm.taobao.org install grunt --no-color --gruntfile Gruntfile.js default'
        sh 'npm --registry https://registry.npm.taobao.org install grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST'   
      }
    }
  }
}

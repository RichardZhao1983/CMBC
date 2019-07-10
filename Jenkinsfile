pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
        sh 'npm --registry https://registry.npm.taobao.org install node-rfc@next'
        sh 'npm --registry https://registry.npm.taobao.org install @sap/grunt-sapui5-bestpractice-build'
        sh 'npm --registry https://registry.npm.taobao.org install grunt-zip'
        sh 'grunt --no-color default'
        sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST'   
      }
    }
  }
}

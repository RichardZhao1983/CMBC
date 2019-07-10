pipeline {
  agent any
  stages {

    stage("Install") {
      steps {
          nodejs('NodeJs') {
          }
          sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
          sh 'npm --registry https://registry.npm.taobao.org install node-rfc@next'
          sh 'npm --registry https://registry.npm.taobao.org install @sap/grunt-sapui5-bestpractice-build'
          sh 'npm --registry https://registry.npm.taobao.org install grunt-zip'    
      }
    }

    stage("Build") {
        steps {
           sh 'grunt --no-color default'
        }
    }

    stage("Deploy") {
        steps {
           sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js createZip uploadToABAP:$TRANSPORT_REQUEST' 
        }
    }
  }
}

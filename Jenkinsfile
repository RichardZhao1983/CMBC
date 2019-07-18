pipeline {
  //agent any
  agent any
  stages {

    stage("Install") {
      steps {
          nodejs('NodeJs') {
          }
          sh 'npm --registry https://registry.npm.taobao.org install -g grunt-cli'
          //sh 'npm --registry https://registry.npm.taobao.org install node-rfc@next'
          //sh 'npm --registry https://registry.npm.taobao.org install @sap/grunt-sapui5-bestpractice-build'
          //sh 'npm --registry https://registry.npm.taobao.org install grunt-zip'
          sh 'npm --registry https://registry.npm.taobao.org install grunt'
      }
    }

    /*stage("Build") {
        steps {
          sh 'grunt --no-color default'
        }
    }

    stage("Zip") {
        steps {
           sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js createZip'
           //zip dir: 'dist/', glob: '', zipFile: 'dist.zip'
        }
    }*/

    stage("Deploy") {
        steps {
          sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js uploadToABAP:123456' 
        }
    }
  }
}

pipeline {
  //agent any
  agent any
  stages {

    stage("Install") {
      steps {
          nodejs('NodeJs') {
          }
          sh 'npm install -g grunt-cli; npm install node-rfc@next; npm install @sap/grunt-sapui5-bestpractice-build; npm install grunt-zip; npm install grunt'
          //sh 'npm --registry https://registry.npm.taobao.org install grunt-zip'
          
      }
    }

    stage("Build") {
        steps {
          sh 'grunt --no-color default'
        }
    }

    stage("Zip") {
        steps {
           sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js createZip'
           //zip dir: 'dist/', glob: '', zipFile: 'dist.zip'
           //archiveArtifacts 'dist.zip'
        }
    }

    stage("Deploy") {
        steps {
          //sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js uploadToABAP:123456' 
          echo 'deploy successfully'
        }
    }
  }
}

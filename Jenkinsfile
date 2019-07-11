pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID     = credentials('jenkins-aws-secret-key-id')
    AWS_SECRET_ACCESS_KEY = credentials('jenkins-aws-secret-access-key')
  }

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
           zip dir: 'dist/', glob: '', zipFile: 'dist.zip'
           sh 'grunt --no-color --gruntfile Gruntfile_ABAP.js uploadToABAP:$TRANSPORT_REQUEST' 
        }
    }
  }
}

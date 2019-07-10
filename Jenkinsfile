pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        nodejs('NodeJs') {
        }
        sh 'echo $PATH'
        sh 'export PATH=/usr/local/bin:/path/to/node:/path/to/node_bin:$PATH;'
        sh 'npm install -g grunt-cli'
        sh 'npm install node-rfc@next'
        sh 'npm install grunt --no-color default'   
      }
    }
  }
}

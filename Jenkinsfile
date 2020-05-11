ipeline {
  agent any
  stages {
     stage('SCM') {
       steps {
         checkout scm
   }
  }
    stage ('install modules'){
      steps{
        sh '''
          npm install --verbose -d 
          npm install --save classlist.js
        '''
      }
    }
    stage ('test'){
      steps{
        sh '''
          ng test --single-run --browsers Chrome_no_sandbox
        '''
      }
      post {
          always {
            junit "test-results.xml"
          }
      }
    }
  }
}

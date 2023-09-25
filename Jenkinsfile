pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-east-1', credentials: '1599e564-5d7f-4a66-bd45-868572b85a2a') {
          s3Upload(bucket: "udacity-jenkins-pipeline", file:'index.html')
        }
      }
    }
  }
}

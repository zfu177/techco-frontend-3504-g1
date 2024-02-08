pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-east-1') {
          sh 'echo "Uploading content with AWS role"'
          s3Upload(
            pathStyleAccessEnabled: true, 
            payloadSigningEnabled: true, 
            file:'.',
            bucket:'group1-static-website'
          )
        }
      }
    }
  }
}

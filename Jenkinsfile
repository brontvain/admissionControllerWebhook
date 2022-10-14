pipeline {
   agent any
   tools {
      go 'go1.15'
   }
   stages {
      stage('test pipeline') {
         steps {
            snykSecurity(
               snykInstallation: 'snyk@latest',
               snykTokenId: 'df6d3cae-0daa-4cbc-b85d-c029dec87453')
               
            cleanWs()
         
            sh(script: """
                  go version
                  echo "hello"
                  git clone https://github.com/brontvain/admissionControllerWebhook
                  cd admissionControllerWebhook/code
                  go build .
               """)
         }
      }
   }
}

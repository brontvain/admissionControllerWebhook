pipeline {
   agent any
   tools {
      go 'go1.15'
   }
   stages {
      stage('test pipeline') {
         steps {
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

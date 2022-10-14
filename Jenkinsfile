pipeline {
   agent any
   tools {
       go '1.15'
   }
   stage('test pipeline') {
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

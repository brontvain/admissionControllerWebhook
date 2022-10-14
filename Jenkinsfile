node('any') {
    
     stage('test pipeline') {
        sh(script: """
           echo "hi"
           git clone https://github.com/brontvain/admissionControllerWebhook
           cd ./code
           
           go build .
        """)
    }
}

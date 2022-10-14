node('') {
    
     stage('test pipeline') {
        cleanWs()
        sh(script: """
           echo "hello"
           git clone https://github.com/brontvain/admissionControllerWebhook
           cd admissionControllerWebhook/code
           
           go build .
        """)
    }
}

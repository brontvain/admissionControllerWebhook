node('Built-In Node') {
    
     stage('test pipeline') {
        sh(script: """
           echo "hello"
           git clone https://github.com/brontvain/admissionControllerWebhook
           cd ./code
           
           go build .
        """)
    }
}

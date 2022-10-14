pipeline {
   agent any
   tools {
      go 'go1.15'
   }
   stages {
      stage('prep') {
         steps {
            echo 'Prepping workspace...'
            cleanWs()
            sh(script: """
                  go version
                  echo "hello"
                  git clone https://github.com/brontvain/admissionControllerWebhook
                  cd admissionControllerWebhook/code
                  pwd
                  """)
         }
      }

      stage('scan') {
         steps {
            echo 'Scanning...'
            dir("${env.WORKSPACE}/admissionControllerWebhook/code") {
            snykSecurity(
               snykInstallation: 'snyk@latest',
               snykTokenId: 'df6d3cae-0daa-4cbc-b85d-c029dec87453',
               failOnError: 'false')
               }
               }
      }

      stage('build') {
         steps { 
           echo 'Building..'
           dir("${env.WORKSPACE}/admissionControllerWebhook/code") {
            sh "go build ."
            println(WORKSPACE)
        }
      }
   } 
}

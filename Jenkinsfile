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
               snykTokenId: 'aaa35ee8-533d-4aec-9b87-8b00a27580c7',
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
}

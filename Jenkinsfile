pipeline {
agent any
tools {
      maven 'maven'
       }
stages {
   stage ('initialize') {
        steps {
            sh '''
             cal 
              ''' 
           }
     }
      stage ('security check'){
            steps {
                sh 'rm tr || true'
                sh 'docker run  --rm --entrypoint  trufflehog cloudkats/trufflehog  https://github.com/redashu/devsecopsjava >tr'
                sh 'cat tr'
            }
      
      
      }
   stage ('Build')
   {
     steps {
       sh 'mvn clean package'
  
       }
   }
 }
}

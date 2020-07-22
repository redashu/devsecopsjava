pipeline {
agent any
tools {
      maven 'maven'
       }
stages {
   stage ('initialize') {
        steps {
            sh '''
              echo  "PATH = ${PATH}"
              echo  "M2_HOME = ${M2_HOME}"
              ''' 
           }
     }
      stage ('security check'){
            steps {
                  sh ''' 
                  rm  trufflehog ||  true 
                  docker run --rm --entrypoint  trufflehog cloudkats/trufflehog  https://github.com/redashu/devsecopsjava >tr
                  cat tr
                 
                   '''
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

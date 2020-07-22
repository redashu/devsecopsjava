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
                sh 'docker run  --rm gesellix/trufflehog  https://github.com/redashu/devsecopsjava >tr'
                sh 'cat tr'
            }
            
      }
      
      stage ('SAST') {
      steps {
        withSonarQubeEnv('sonar') {
          sh 'mvn sonar:sonar'
          sh 'cat target/sonar/report-task.txt'
               }
          }
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

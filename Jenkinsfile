pipeline {
agent any
tools {
      maven 'Maven'
       }
stages ('Initialize')  {

  steps {
      sh '''
        echo  "PATH = ${PATH}"
        echo  "M2_HOME = ${M2_HOME}"
        ''' 
      }
  }
stages ('Build')
{
  steps {
    sh 'mvn clean package'
  
   }

 }
}

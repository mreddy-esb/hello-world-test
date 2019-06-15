pipeline {
  agent any
  stages {
  
   stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }
    
    stage('Deploy ARM') { 
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials') 
      }
      steps {
        bat 'mvn deploy -X -P arm -Dusername=${ANYPOINT_CREDENTIALS_USR}  -Dpassword=${ANYPOINT_CREDENTIALS_PSW}' 
      }
    }
  }
}
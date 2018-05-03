pipeline {
  agent any
  stages {
    stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }
    stage('Deploy to CloudHub') { 
      steps { 
        bat 'mvn deploy -P cloudhub' 
      }
    }
    
    stage('Deploy ARM') { 
     
      steps {
        bat 'mvn deploy -P arm -Darm.target.name=standAlone3.9.1' 
      }
    }
    
    
  }
}
















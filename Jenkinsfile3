pipeline {
  agent any
  stages {

    stage('Build') {
      steps {
        echo 'Pulling...' + env.BRANCH_NAME
        checkout scm

      }
   }

    stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }
    
  }
}
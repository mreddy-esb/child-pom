pipeline {
  agent any
  stages {

    stage('Build') {
      node {
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
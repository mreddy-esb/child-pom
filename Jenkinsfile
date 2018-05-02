pipeline {
  agent any
  stages {
    stage('Unit Test') { 
      steps {
        sh 'mvn clean test'
      }
    }
    stage('Deploy Cloudhub') { 
      steps {
        sh 'mvn deploy -P cloudhub'
      }
    }
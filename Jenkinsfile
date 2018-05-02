pipeline {
  agent any
  stages {



     stage('Preparation') { // for display purposes

      git url: "https://github.com/mreddy-esb/child-pom.git", branch: env.BRANCH_NAME

      bat(/git clean -f/)

      bat(/git reset --hard/)

      bat(/git checkout ./)

      mvnHome = tool 'M3'

   } 



    stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }



    
  }
}
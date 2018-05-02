pipeline {
  agent any
  
  tools {
        maven 'M3'
        jdk 'Java 8'
    }
    
    
  stages {
    stage('Unit Test') { 
      steps {
        bat 'mvn clean test'
      }
    }
    stage('Deploy CloudHub') { 
      steps { 
        bat 'mvn deploy -P cloudhub' 
      }
    }
  }
}



def mvn(args) {
    withMaven(
        // Maven installation declared in the Jenkins "Global Tool Configuration"
        maven: 'M3',
        // Maven settings.xml file defined with the Jenkins Config File Provider Plugin
        
        // settings.xml referencing the GitHub Artifactory repositories
         mavenMySettings: 'c1c27aab-9532-4f6c-a989-83d32425b586',
        // we do not need to set a special local maven repo, take the one from the standard box
        //mavenLocalRepo: '.repository'
        ) {
        // Run the maven build
        bat "mvn $args -Dmaven.test.failure.ignore"
    }
}
pipeline {
    agent any

    stages {
        stage ('Compile and Testing Stage') {

            steps {
                withMaven(maven : 'M3') {
                
        configFileProvider(
        [configFile(fileId: 'maven-settings', variable: 'C:\Users\Dad\.m2')]) {
        bat 'mvn -s $MAVEN_SETTINGS clean package'
    }
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'M3') {
                    bat 'mvn deploy -P cloudhub'
                }
            }
        }
    }
}
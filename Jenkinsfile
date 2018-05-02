pipeline {
    agent any

    stages {
        stage ('Compile and Testing Stage') {

            steps {
                withMaven(maven : 'M3') {
           
        configFileProvider(
        [configFile(fileId: 'e3cfa9aa-8870-4a4b-91ae-c7b929c7f7e1', variable: 'MAVEN_SETTINGS')]) {
        bat 'mvn -s $M2_HOME/conf/settings.xml clean package'
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
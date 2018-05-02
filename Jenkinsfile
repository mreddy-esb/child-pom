pipeline {
    agent any

    stages {
        stage ('Compile and Testing Stage') {

            steps {
                withMaven(maven : 'M3') {
                
        configFileProvider(
        [configFile(fileId: 'e3cfa9aa-8870-4a4b-91ae-c7b929c7f7e1', variable: 'MySettings')]) {
        bat 'mvn -s settings.xml clean package'
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
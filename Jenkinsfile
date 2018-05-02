pipeline {
    agent any

    stages {
        stage ('Compile and Testing Stage') {

            steps {
                withMaven(maven : 'M3') {
                
        configFileProvider(
        [configFile(fileId: 'e3cfa9aa-8870-4a4b-91ae-c7b929c7f7e1', variable: 'C:/Program Files (x86)/apache-maven-3.5.0/conf')]) {
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
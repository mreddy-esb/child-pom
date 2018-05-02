pipeline {
    agent any

    stages {
        stage ('Compile and Testing Stage') {

            steps {
                withMaven(maven : 'M3') {
                
        configFileProvider(
        [configFile(fileId: '265f10a3-08d1-4894-9e76-d346c338c37e', variable: 'MySettings')]) {
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
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               mvn 'clean package'
            }
        }
        stage('Deploy'){
            steps{
                deploy adapters: [tomcat8(credentialsId: 'TomcatCreds', path: '', url: 'http://localhost:8080')], contextPath: null, onFailure: false, war: '**/*.war'
            }
        }
    }
}

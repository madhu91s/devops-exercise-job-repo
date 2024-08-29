pipeline {
    agent {label 'agent'}

    stages {
        stage('Build') {
            steps {
                checkout scm
                bat "mvn package"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test"
            }
        }
        stage('Archive'){
            steps {
                archiveArtifacts artifacts: '*.jar', allowEmptyArchive: true
            }
        }
    }

}

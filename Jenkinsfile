pipeline {
    agent {label 'agent'}

    stages {
        stage('Build') {
            steps {
                checkout scm
                bat "mvn build"
            }
        }
        stage('Test') {
            steps {
                bat "mvn runTests"
            }
        }
        stage('Archive'){
            steps {
                archiveArtifacts artifacts: '*.jlar', allowEmptyArchive: true
            }
        }
    }

}

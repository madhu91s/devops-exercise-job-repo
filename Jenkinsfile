pipeline {
    agent {label 'agent'}

    stages {
        stage('Build') {
            steps {
                scm checkout
                sh "mvn build"
            }
        }
        stage('Test') {
            steps {
                sh "mvn runTests"
            }
        }
        stage('Archive'){
            steps {
                archiveArtifacts artifacts: '*.jlar', allowEmptyArchive: true
            }
        }
    }

}

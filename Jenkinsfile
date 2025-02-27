pipeline {
    agent any
    stages {

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run Cypress Tests') {
            steps {
                sh 'npx cypress run || true'
            }
        }
         stage('Archive Reports') {
             steps {
                 archiveArtifacts artifacts: 'cypress/screenshots/**/*', allowEmptyArchive: true
             }
         }
    }

    post {
        always{
            echo 'Pipeline terminé'
        }
        success {
            echo 'Pipeline réussie'
        }
        failure {
            echo 'Pipeline échouée'
        }
    }
}
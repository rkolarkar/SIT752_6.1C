pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production... test'
            }
        }
    }
    post {
        success {
            echo 'Pipeline succeeded!'
            emailext attachLog: true,
                recipientProviders: "s223742152@deakin.edu.au",
                subject: "Jenkins Pipeline Success: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline ${currentBuild.fullDisplayName} was successful."
        }
        failure {
            echo 'Pipeline failed!'
            emailext attachLog: true,
                to: "s223742152@deakin.edu.au",
                subject: "Jenkins Pipeline Failure: ${currentBuild.fullDisplayName}",
                body: "The Jenkins pipeline ${currentBuild.fullDisplayName} failed. Please review the attached logs."
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code... test'
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
                echo 'Deploying to production...'
            }
        }
    }
    post {
        always {
            emailext (
		 to: 's223742152@deakin.edu.au',
                 subject: "Pipeline Status: ${currentBuild.currentResult}",
                 body: "Pipeline finished with status: ${currentBuild.currentResult}",
                 attachmentsPattern: '**/log'
	   )
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code(Tools like Maven and Gradle)..'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests (Tools like TestNG, Selenium)..'
            }
            post {
        success {
            echo 'Successfully Completed Unit and Integration Tests!'
            emailext attachLog: true,
                to: "s223742152@deakin.edu.au",
                subject: "Unit and Integration Tests Success: ${currentBuild.fullDisplayName}",
                body: "The Unit and Integration Tests ${currentBuild.fullDisplayName} was successful."
        }
        failure {
            echo 'Faliure on execution of Unit and Integration Tests!'
            emailext attachLog: true,
                to: "s223742152@deakin.edu.au",
                subject: "Unit and Integration Tests Failure: ${currentBuild.fullDisplayName}",
                body: "The Unit and Integration Tests ${currentBuild.fullDisplayName} failed. Please review the attached logs."
        }
    }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis(Tool: SonarQube)..'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan(Tools: OWASP ZAP or Snyk)..'
            }
                post {
        success {
            echo 'Successfully completed security scan!'
            emailext attachLog: true,
                to: "s223742152@deakin.edu.au",
                subject: "security scan Success: ${currentBuild.fullDisplayName}",
                body: "The security scan ${currentBuild.fullDisplayName} was successful."
        }
        failure {
            echo 'Faliure on execution of security scan!'
            emailext attachLog: true,
                to: "s223742152@deakin.edu.au",
                subject: "security scan Failure: ${currentBuild.fullDisplayName}",
                body: "The security scan ${currentBuild.fullDisplayName} failed. Please review the attached logs."
        }
    }

        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging (AWS EC2 instance using Terraform)'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging(Postman for API Testing)..'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production... test'
            }
        }
    }
}

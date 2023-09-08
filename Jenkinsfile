pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package' // Use 'bat' instead of 'sh' for Windows batch command
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                bat 'run_unit_tests.bat' // Use 'bat' for Windows batch command
                bat 'run_integration_tests.bat' // Use 'bat' for Windows batch command
            }
        }
        stage('Code Analysis') {
            steps {
                bat 'sonar-scanner.bat' // Use 'bat' for Windows batch command
            }
        }
        stage('Security Scan') {
            steps {
                bat 'run_security_scan.bat' // Use 'bat' for Windows batch command
            }
        }
        stage('Deploy to Staging') {
            steps {
                bat 'deploy_to_staging.bat' // Use 'bat' for Windows batch command
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                bat 'run_integration_tests_on_staging.bat' // Use 'bat' for Windows batch command
            }
        }
        stage('Deploy to Production') {
            steps {
                bat 'deploy_to_production.bat' // Use 'bat' for Windows batch command
            }
        }
    }
    
    post {
        failure {
            // Handle failure scenarios if needed
            echo 'Pipeline failed, take appropriate action.'
        }
        success {
            // Send notifications or perform actions upon successful completion
            echo 'Pipeline succeeded. Deployment to production can be manually triggered.'
        }
    }
}

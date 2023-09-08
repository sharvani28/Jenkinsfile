pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "C:\\Users\\sharv\\OneDrive\\Desktop\\Jenkinsfile"
        TESTING_ENVIRONMENT = "testing-environment"
        PRODUCTION_ENVIRONMENT = "sharvani-production"
    }
    stages {
        stage('Build') {
            steps {
                echo "Build the code using a build automation tool to compile and package your code. Tool: Maven"
                
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected. Tools: JUnit (Unit Tests), Selenium (Integration Tests)"
            }
            post{
        always{
            emailext to: "sharvanikandala@gmail.com",
            subject: "Test Email",
            body: "Test",
            attachLog: true
        }
    }
        }
        
        stage('Code Analysis') {
            steps {
                echo "Integrate a code analysis tool to analyse the code and ensure it meets industry standards. Tool: SonarQube "
            }
        }
        
        stage('Security Scan') {
            steps {
                echo "Perform a security scan on the code using a tool to identify any vulnerabilities. Tool: OWASP ZAP "
            }
	    post{
               always{
            emailext to: "sharvanikandala@gmail.com",
            subject: "Security scan Email",
            body: "Security Scan successful",
            attachLog: true
        }
    }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to a staging server (e.g., AWS EC2 instance)."
                
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo "Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment."
            }
        }
	stage('Deploy to Production') {
            steps {
                echo "Deploy the application to a production server (e.g., AWS EC2 instance)."
            }
        }
    }
}

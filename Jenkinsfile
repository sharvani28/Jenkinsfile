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
                echo "Fetching the source code from the directory path specified by the environment variable"
                echo "Compiling the code and generating any necessary artifacts"
            }
        }
        
        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }
        
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable"
            }
        }
        
        stage('Approval') {
            steps {
                echo "Waiting for manual approval..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Deploy the code to the production environment using the environment variable specifying the environment name"
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building using Maven ..."
            }
        }
        
        stage("Unit and Integration Tests") {
            steps {
                echo "Running unit tests with JUnit ..."
                echo "Running integration tests ..."
                echo "Making change example ..."
            }
            post{
                always{
                    mail to: "Robert.Tkatchenko@gmail.com",
                    subject: "Unit and Integration Status Email",
                    body: "Tests log attached!"
                }
            }
        }

        stage("Code Analysis") {
            steps {
                echo "Analyzing code with SonarQube ..."
            }
        }

        stage("Security Scan") {
            steps {
                echo "Scanning for security vulnerabilities with OWASP ZAP ..."
            }
            post{
                always{
                    mail to: "Robert.Tkatchenko@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "Tests log attached!"
                }
            }
        }

        stage("Deploy to Staging") {
            steps {
                echo "Deploying to staging server (e.g., AWS EC2) ..."
            }
        }

        stage("Integration Tests on Staging") {
            steps {
                echo "Running integration tests on staging ..."
            }
        }

        stage("Deploy to Production") {
            steps {
                echo "Deploying to production server (e.g., AWS EC2) ..."
            }
        }
    }
    
    post {
        success {
            echo "Pipeline completed successfully!"
        }
        failure {
            echo "Pipeline failed. Please check the logs for details."
        }
    }
}

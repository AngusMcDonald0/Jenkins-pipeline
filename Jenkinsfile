pipeline {
    agent any
    stages {
        stage("Build") {
            steps { 
                echo "Build autometed with Maven"
            }
        }
        stage("Unit and Integration Tests") {
            steps { 
                echo "Automated tests with Selenium"
            }
            post {
                success {
                    mail to: "angusmcdonald13@gmail.com",
                    subject: "Security scan",
                    body: "Tests successful"
                }
            }
        }
        stage("Code Analysis") {
            steps { 
                echo "Check the quality of the code with jenkins plugin for CheckStyle"
            }
        }
        stage("Security Scan") {
            steps { 
                echo "code scanned with CodeQL to identify vulnerabilities"
            }
            post {
                success {
                    emailext(attachLog: true, body: '', subject: '', mail to: "angusmcdonald13@gmail.com")
                    // mail to: "angusmcdonald13@gmail.com",
                    // subject: "Security scan",
                    // body: 'david might be wrong',
                    // attachLog: true
                }
            }
        }
        stage("Deploy to Staging") {
            steps { 
                echo "Code deployed to staging server"
            }
        }
        stage("Integration Tests on Staging") {
            steps { 
                echo "Integration tests run"
            }
        }
        stage("Deploy to Production") {
            steps { 
                echo "Code deployed to production server"
            }
        }
    }
}
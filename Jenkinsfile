pipeline {
    agent any
    environment {
        // Define environment variables if needed
    }
    stages {
        stage('Build') {
            steps {
                echo 'Build using Maven'
                // Example: sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests using JUnit and Selenium'
                // Example: sh 'mvn test'
            }
            post {
                always {
                    mail to: 'mahirseth123@gmail.com',
                        subject: "Unit and Integration Tests - Build ${currentBuild.fullDisplayName}",
                        body: "Unit and Integration Tests completed. Check console output at ${env.BUILD_URL} to view the results."
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube'
                // Example: sh 'mvn sonar:sonar'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scanning with OWASP ZAP'
                // Example: sh 'zap-cli start scan'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
                // Example: sh 'deploy-script.sh staging'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration testing in staging'
                // Example: sh 'selenium-test.sh'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
                // Example: sh 'deploy-script.sh production'
            }
            post {
                success {
                    mail to: 'mahirseth123@gmail.com',
                        subject: "Production Deployment - Build ${currentBuild.fullDisplayName} Successful",
                        body: "Production deployment was successful. Check console output at ${env.BUILD_URL} to view the results."
                }
                failure {
                    mail to: 'mahirseth123@gmail.com',
                        subject: "Production Deployment - Build ${currentBuild.fullDisplayName} Failed",
                        body: "Production deployment failed. Check console output at ${env.BUILD_URL} to view the results."
                }
            }
        }
    }
}

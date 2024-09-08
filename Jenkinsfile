pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build using Maven'
                // Tool: Maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running tests using JUnit and Selenium'
                // Tools: JUnit for unit tests, Selenium for integration tests
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code with SonarQube'
                // Tool: SonarQube
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Security scanning with OWASP ZAP'
                // Tool: OWASP ZAP
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to AWS EC2 (staging)'
                // Tool: AWS EC2, Jenkins deploy plugin
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Integration testing in staging'
                // Tool: Selenium
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to AWS EC2 (production)'
                // Tool: AWS EC2, Jenkins deploy plugin
            }
        }
    }
    post {
        always {
            mail to: 'your.email@example.com',
                subject: "Build ${currentBuild.fullDisplayName} finished",
                body: "Check console output at ${env.BUILD_URL} to view the results."
        }
    }
}

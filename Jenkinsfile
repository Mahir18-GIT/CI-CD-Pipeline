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
                // Tool: SonarQube for analysing
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
    success {
        mail to: 'mahirseth123@gmail.com',
            subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - SUCCESS",
            body: "Build was successful! Check console output at ${env.BUILD_URL} to view the results."
    }
    failure {
        mail to: 'mahirseth123@gmail.com',
            subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - FAILURE",
            body: "Build failed. Check console output at ${env.BUILD_URL} to view the results and diagnose issues."
    }
    unstable {
        mail to: 'mahirseth123@gmail.com',
            subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - UNSTABLE",
            body: "Build is unstable. There might be some issues. Check console output at ${env.BUILD_URL}."
    }
    changed {
        mail to: 'mahirseth123@gmail.com',
            subject: "${env.JOB_NAME} - Build #${env.BUILD_NUMBER} - CHANGED",
            body: "Build status changed. Previous build was different. Check ${env.BUILD_URL} for more details."
    }
}
}
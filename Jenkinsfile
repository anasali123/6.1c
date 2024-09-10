pipeline {
    agent any
    environment {
        DIRECTORY_PATH = "${env.WORKSPACE}/src"
        STAGING_SERVER = 'AWS Staging EC2'
        PRODUCTION_SERVER = 'AWS Production EC2'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit tests and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis using SonarQube...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running security scan using OWASP Dependency Check...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to ${STAGING_SERVER}..."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying to ${PRODUCTION_SERVER}..."
            }
        }
    }
    post {
        always {
            mail bcc: '', body: "Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}", cc: '', from: '', replyTo: '', subject: "Jenkins Pipeline Result", to: 'syedanasali0478@gmail.com'
        }
    }
}

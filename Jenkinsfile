pipeline {
    agent any
    
    tools {
        nodejs 'NodeJS' // Name of your NodeJS installation in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from GitHub
                git url: 'https://github.com/jeevan-v8/Building-an-AI-wallpaper-generator',
                branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }

        stage('Build with Maven') {
            steps {
                // Build the application using Maven
                sh 'mvn clean package'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                // Run Selenium tests
                // This assumes you have a Maven test setup
                // Adjust the command according to your test class setup
                sh 'mvn test -Dtest=YourSeleniumTestClass'
            }
        }
    }

    post {
        success {
            echo 'Build and tests were successful!'
        }

        failure {
            echo 'Build or tests failed!'
        }

        always {
            // Clean up or send notifications
            echo 'Cleaning up...'
        }
    }
}
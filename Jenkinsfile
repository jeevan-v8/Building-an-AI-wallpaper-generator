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
    }

    post {
        success {
            echo 'Build and tests were successful!'
        }
    }
}
pipeline {
    agent any

    environment {
        NODEJS_HOME = tool name: 'NodeJS 14' // Ensure this matches the name you set in Global Tool Configuration
        PATH = "${env.NODEJS_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the repository and check out the 'main' branch
                git branch: 'main', url: 'https://github.com/abdullahzahid39/React-Quiz-App.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Run tests (if any)
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                // Build the application (if needed)
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                // Start the application using pm2 or a similar tool
                // Ensure pm2 is installed and configured on the system
                sh 'nohup npm start &' // Ensure this command starts your application correctly
                echo "Deployment started"
            }
        }
    }
}

pipeline {
    agent {
        label 'prod-server'
    }

    stages {
        stage('Clone') {
            steps {
                // Pull the latest code from GitHub
                git branch: 'main', credentialsId: 'e4aa4398-3d7d-4b33-9af6-e5e0fbef2a18', url: 'git@github.com:majharuli0/OSTAD-Assignment-module-3.git'
            }
        }

        stage('Install') {
            steps {
                // Install dependencies using npm
                sh 'ls'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                // Run the tests
                sh 'npm run check'
            }
        }

        stage('Ensure Test Results') {
            steps {
                // If `npm run check` fails, Jenkins will mark the build as failed.
                // This is a placeholder stage to ensure the tests results show up in the console output.
                echo 'Test results will be displayed in the Jenkins console output.'
            }
        }
    }

    post {
        failure {
            echo 'Tests failed! Marking pipeline as failed.'
        }
    }
}

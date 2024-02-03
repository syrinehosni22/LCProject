pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here (e.g., copy files to a server)
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'npm test'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and test successful! Deploying...'
            // Add deployment steps or notifications on success
        }
        failure {
            echo 'Build or test failed! Notify the team...'
            // Add notification steps or rollback actions on failure
        }
    }
}
// test 6
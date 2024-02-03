pipeline {
    agent any

    environment {
        // Set your environment variables here
        NODEJS_HOME = tool 'NodeJS' // Assuming you have NodeJS tool configured in Jenkins
        PATH = "${NODEJS_HOME}/bin:${PATH}"
        NPM_REGISTRY = 'https://registry.npmjs.org/' // Replace with your npm registry
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'npm install --registry $NPM_REGISTRY'
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

      //   stage('Deploy') {
      //       steps {
      //           // Add your deployment steps here (e.g., copy files to a server)
      //       }
      //   }

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
// test 1
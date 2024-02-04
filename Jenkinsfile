pipeline {
    agent any
     environment {
        NODEJS_HOME = tool 'NodeJS'
        PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Users\\User\\AppData\\Roaming\\npm;"
        NPM_REGISTRY = 'https://registry.npmjs.org/'
    }
      tools {nodejs "NodeJS"}


    stages {
       stage('install dependency') {
            steps {
               dir('C:/Users/User/LCProject') {
                 script {
                     bat 'npm install --legacy-peer-deps'
                }
               }
              
            }
        }
         stage('Test') {
            steps {
                dir('C:/Users/User/LCProject') {
                script {
                    echo 'Hello, this is a test!'
                }
            }
        }
        }
        stage('Build') {
            steps {
                dir('C:/Users/User/LCProject') {
                script {
                    bat 'npm run build'
                }
                }
             }
        }

        stage('Deploy') {
            steps {
                  echo 'Hello, this is a test!'
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
// test 5
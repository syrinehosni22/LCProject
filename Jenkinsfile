pipeline {
    agent any
     environment {
        NODEJS_HOME = tool 'NodeJS'
        PATH = "C:\\WINDOWS\\SYSTEM32;C:\\Users\\User\\AppData\\Roaming\\npm;"
        NPM_REGISTRY = 'https://registry.npmjs.org/'
    }
      tools {nodejs "NodeJS"}


    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        //  stage('install spetial dependency') {
        //     steps {
        //        dir('C:/Users/User/LCProject') {
        //          script {
        //              bat 'npm install  @angular-devkit/build-angular --legacy-peer-deps'
        //         }
        //        }
              
        //     }
        // }

       stage('install dependency') {
            steps {
               dir('C:/Users/User/LCProject') {
                 script {
                     bat 'npm install --legacy-peer-deps'
                }
               }
              
            }
        }

        stage('Build') {
            steps {
                script {
                    bat 'npm run build'
                }
            }
        }

        // stage('Deploy') {
        //     steps {
        //         // Add your deployment steps here (e.g., copy files to a server)
        //     }
        // }

        stage('Test') {
            steps {
                script {
                    bat 'npm test'
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
// test 2
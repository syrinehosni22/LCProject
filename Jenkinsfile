pipeline {
   agent any
   stages {
    stage('Checkout') {
      steps {
        script {
           git branch: 'syrinetyb', 
           url: 'https://github.com/syrinehosni/LCProject.git'
          }
       }
    }
    stage('Build') {
      steps {
        script {
           sh 'ansible-playbook ansible/build.yml -i ansible/inventory/hosts.yml'
          }
       }
    }
  }
}
// test build
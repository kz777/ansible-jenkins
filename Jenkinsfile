pipeline {
   agent any

   stages {
      
      stage('SCM Checkout') {
         steps {
             git 'https://github.com/kz777/ansible-jenkins'
         }
      }
      stage('run ansible') {
         steps {
            //  sh 'ansible webservers -m ping'
            ansiblePlaybook become: true, credentialsId: 'root', disableHostKeyChecking: true, installation: 'ansible', inventory: 'inventory', playbook: 'apache2-playbook.yaml'
         }
      }
   }
}

pipeline {
 
agent any 
    
  stages {
   
   // Testando Docker
   // Inicia agent com Docker e verifica versão Node
    stage('Teste Docker') {
     agent { docker { image 'node' } }
            steps {
                sh 'node --version'
            }
        }
     
     // Logando no servidor destino
     // Credencial criada em Gerenciar Jenkins > Manage Credentials
     // Fonte: https://blog.devgenius.io/how-i-can-make-ssh-from-server-to-jenkins-8dcc34647c6b
     // Webhook https://pipeline.**/github-webhook/
     // Com Webhook configurado no repositório e habilitado opção "Github hook trigger for GITScm Polling" no Build Triggers qualquer commit envia para Jenkins
        
     stage('Logando'){
         
       steps{
            sshagent(credentials:['90173669-204f-456a-ab02-d1d9c81a784c']){
               sh 'ssh  -o StrictHostKeyChecking=no  ubuntu@18.215.143.84 uptime "whoami"'
               sh 'whoami && hostname'
          }
        echo "Logado com sucesso!"
       }
       
     }
   
     
     
     // Processo de Building
     stage('Build') {
            steps {
                echo "Buildado!"  
            }
        }
     
     
     
     
      // Processo de Testing
      stage('Test') {
            steps {
               echo "Testado!"  
            }
        }
    
     
     // Processo de Deploy
     stage('Deploy') {
            when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                echo "Deployado!"
            }
        }
     
     
 }
}

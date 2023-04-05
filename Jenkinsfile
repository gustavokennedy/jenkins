agent any

stages {
  
  stage('Checkout Github') {
    steps {
      git url: 'https://github.com/gustavokennedy/jenkins.git', branch: 'main' 
    }
  }
  
  stage('Criação/Atualização Infraestrutura'){
    steps{
      script {
        dir('src') {
          sh 'ls'
        }
      }
    }
    
  }
}

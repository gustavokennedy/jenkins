pipeline {
  agent any
  stages {
    
    
      stage('Checkout Github') {
    steps {
      git url: 'https://github.com/gustavokennedy/jenkins.git', branch: 'main' 
    }
  }
    
    stage("Teste") {
      steps {
        sh "ls"
      }
    }
    
  }
}

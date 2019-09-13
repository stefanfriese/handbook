pipeline {
  agent any
  
  stages {
    
    stage('Lint HTML') {
        steps {
            echo 'Static Code Check...'
            sh 'tidy -q -e *.html'
        }
    }
    
  }
}

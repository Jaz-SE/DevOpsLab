pipeline {
  agent any

  stages {
      stage('Build') {
        steps {
          script {
            echo 'Building...'
            ls
            pwd
          }
        }
      }
      stage('Test') {
        steps {
          script {
            echo 'Testing...'
            touch 'testfile.txt'
            ls
          }
        }
      } 
      stage('Deploy') {
        steps {
          script {
            echo 'Deploying...'
            mv 'testfile.txt' 'deployedfile.txt'
            ls
          }
        }
      }
  }
  post {
    always {
      archiveArtifacts artifacts: 'deployedfile.txt', allowEmptyArchive: true
    }
  }
}
            

pipeline {
  agent 'helm'
  stages {
    stage('Helm') {
      steps {
        container('helm') {
          sh 'helm template test-app'
        }
      }
    }
  }
}

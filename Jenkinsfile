pipeline {
  agent {
    label 'helm'
  }
  stages {
    stage('Helm') {
      steps {
        container('helm') {
          sh '''
            #!/bin/bash
            HELM_CHART_VERSION=$(yq e ".version" test-app/Chart.yaml)
            echo "HELM_CHART_VERSION: ${HELM_CHART_VERSION}"
            helm template test-app
            helm lint test-app
            helm package test-app/ --destination package/ --version ${HELM_CHART_VERSION}
          '''
        }
      }
    }
  }
}

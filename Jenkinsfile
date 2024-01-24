pipeline {
  agent {label ''}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        echo "Hello"
        sh './gradlew clean check --no-daemon'
      }
    }
  }
  post {
    always {
        junit(
          allowEmptyResults: true, 
          testResults: '**/build/test-results/test/*.xml'
        )
    }
  }
}

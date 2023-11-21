pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/afsara-tasnim/sample_project', branch: 'main', poll: true)
      }
    }

  }
}
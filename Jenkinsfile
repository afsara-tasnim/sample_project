pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git(url: 'https://github.com/afsara-tasnim/sample_project', branch: 'main', poll: true)
      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('Build') {
      steps {
        sh 'docker buildx build --build-context project=https://github.com/afsara-tasnim/sample_project . -t afsara813/website:latest'
      }
    }

    stage('Docker log In') {
      environment {
        Dockerhub = 'afsara813'
        Dockerhub_Pass = 'Lalaland#3'
      }
      steps {
        sh 'docker login -u $Dockerhub -p $Dockerhub_Pass'
      }
    }

    stage('Push') {
      steps {
        sh 'docker push afsara813/website:latest'
      }
    }

  }
}
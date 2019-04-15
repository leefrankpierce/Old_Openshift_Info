pipeline {
  agent { label 'docker' }
  stages {
    stage('checkout') {
      steps {
      checkout scm
      }
    }
    stage('Build') {
      steps {
        sh "docker build -t leedogs ."
      }
    }
    stage('Publish') {
      steps {
          sh "docker login -u leefrankpierce
          sh "docker push leedogs"
        }
      }
    }
}



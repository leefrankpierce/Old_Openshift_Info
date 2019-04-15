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
        sh "docker build -t leefrankpierce/leedogs ."
      }
    }
    stage('Publish') {
      steps {
          sh "docker login -u leefrankpierce -p leefrankpierce"
          sh "docker image push leefrankpierce/leedogs"
        }
      }
    }
}



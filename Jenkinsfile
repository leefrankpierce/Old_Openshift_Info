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
      when {
        branch 'master'
      }
      steps {
          sh "docker push leefrankpierce/leedogs"
        }
      }
    }
}



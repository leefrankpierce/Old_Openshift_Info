pipeline {
  agent { label 'docker' }
  stages {
    stage('checkout') {
      step{
      checkout scm
      }
    }
    stage('Build') {
      step{
        app = docker.build("leefrankpierce/leedogs")
      }
    }
  }
}

pipeline {
  agent { label 'docker' }
  stages {
    stage('checkout') {
      checkout scm
    }
    stage('Build') {
        app = docker.build("leefrankpierce/leedogs")
    }
  }
}

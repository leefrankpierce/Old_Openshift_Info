pipeline {
  agent { label 'docker' }
  stages {
    stage('checkout') {
      steps {
      checkout scm
      }
    }
    stage('Build') {
      
        app = docker.build("leefrankpierce/leedogs")
      
    }
    /*stage('Publish') {
      steps {
          sh "docker login -u leefrankpierce -p leefrankpierce"
          sh "docker image push leefrankpierce/leedogs"
        }
      } 
    } */
}



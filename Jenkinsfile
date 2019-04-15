pipeline {
  agent { label 'docker' }
  options {
    ansiColor colorMapName: 'XTerm'
  }
  stages {
    stage('checkout') {
      checkout scm
    }
    stage('Build') {
      steps {
        sh "docker build -t leedogs:${GIT_SHA} ."
      }
    }
    stage('Publish') {
      when {
        branch 'master'
      }
      steps {
          sh "docker push leefrankpierce/leedogs:${GIT_SHA}"
        }
      }
    }
  



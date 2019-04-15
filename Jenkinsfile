pipeline {
  agent { label 'docker' }
  options {
    ansiColor colorMapName: 'XTerm'
  }
  stages {
    stage('Build') {
      steps {
        sh "docker build -t https://github.com/leefrankpierce/leedogs:${GIT_SHA} ."
      }
    }
    stage('Publish') {
      when {
        branch 'master'
      }
      steps {
#        withDockerRegistry([credentialsId: 'registry-creds', url: 'https://registry.yourcompany.com']) {
          sh "docker push leefrankpierce/leedogs:${GIT_SHA}"
        }
      }
    }
  }
}


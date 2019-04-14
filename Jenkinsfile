pipeline {
    agent {
        dockerfile true
    }
    stages {
        stage('Build') {
            steps {
                script { docker.build = dog}
            }
        }
    }
}

pipeline {
    agent {
        dockerfile true
    }
    stages {
        stage('Build') {
            steps {
                script {
                    image = docker.build("${IMAGE}")
                    println "Newly generated image, " + image.id
                }
            }
        }
    }
}

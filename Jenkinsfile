node ('docker') {
    def app 
   /* the "docker" above notes the build server I have configured from inside Jenkins */
    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

	docker.withRegistry('https://registry.hub.docker.com', 'leedockerhub') {	
        app = docker.build("leefrankpierce/leedogs")
	}
      }

    stage('Test image') {
        
        app.inside {
            echo "Tests passed"
        }
    }

    stage('Push image') {
        /* 
			You would need to first register with DockerHub before you can push images to your account
		*/
        docker.withRegistry('https://registry.hub.docker.com', 'leedockerhub') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
            } 
                echo "Trying to Push Docker Build to DockerHub"
    }
}

 

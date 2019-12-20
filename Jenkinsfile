pipeline {
    agent {
  label 'amzn-lnx-slave'
}

	 stages {
        stage('CreteDockerContainer') { 
            steps {
                // 
				sh "whoami"
				sh "docker --version"
		    		sh "docker container prune"
		    		sh "docker rm -f "
				sh "docker run -itd -p 90:80 nginx"
            }
        }
        stage('ViewRunningContainers') { 
            steps {
                //
				
				sh "docker ps -a"
            }
        }
        stage('Verify') { 
            steps {
                // 
				
				sh "docker inspect "
            }
        }
    }
}

pipeline {
       agent {
  label 'slave1'
} 
	
	
    stages {
	
		stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/sforcloud/docker-sample-website.git"
            }
			}
        stage('Build') { 
            steps {
                echo "hello Build Stage"
				sh "docker build -t jenkins-docker ."
            }
        }
        stage('Tag') { 
            steps {
                echo "hello Tag Stage"
				sh "docker tag jenkins-docker sforcloud/jenkins-image"
				
            }
        }
        stage('Login') { 
            steps {
                echo "Hello Login Stage"
				sh "docker login --username=sforcloud --password=Asus12345"
            }
        }
		stage('Push') { 
            steps {
                echo "Hello Pushing Image to DockerHub"
				sh "docker push sforcloud/jenkins-image"
            }
        }
    }
}

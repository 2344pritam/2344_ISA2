pipeline {
    agent any  // Use any available agent

    stages {
        stage('Clone repository') {
            steps {
                script {
                    git 'https://github.com/2344pritam/2344_ISA2.git'
                }
            }
        }
		
	stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image from the Dockerfile in the current directory
                    docker.build('2344_image')
                }
            }
        }
		
        stage('Deploy Container') {
            steps {
                script {
                    // Remove any existing container with the same name to avoid conflicts
                    sh 'docker rm -f 2344 || true'
					sh 'docker run -d --name 2344 -p 5000:50000 2344_image'
            }
        }
    }
}
    }
}

pipeline {  
    agent any  


    stages {  
        stage('Clone Repository') {  
            steps {  
                // Checkout the repository containing the Dockerfile  
                git branch: 'main', url: 'https://github.com/2344pritam/2344_ISA2.git'  
            }  
        }  

        stage('Build Docker Image') {  
            steps {  
                script {  
                    // Build the Docker image  
                    bat "docker build -t mca2344/2344_isa2 ."
                }  
            }  
        }    
    }  

    post {  
        always {  
            // Clean up workspace  
            cleanWs()  
        }  
        success {  
            echo "Docker image built successfully."  
        }  
        failure {  
            echo "There was an error building the Docker image."  
        }  
    }  
}

pipeline {  
    agent any  

    stages {  
        stage('Clone Repository') {  
            steps {  
    
                git branch: 'main', url: 'https://github.com/2344pritam/2344_ISA2.git'  
            }  
        }  



    

        stage('Build Docker Image') {  
            steps {  
                script {  
                    bat "docker build -t mca2344/2344_isa2 ."
                }  
            }  
        }    
    }  

    post {  
        always {   
            cleanWs()  
        }  
        success {  
            echo "Docker image got built successfully."  
        }  
        failure {  
            echo "Error occured building the Docker image."  
        }  
    }  
}

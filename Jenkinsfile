pipeline {
    agent any

    environment {
        IMAGE_NAME = "marwanalanani/python-app-image "
    }

    stages {
        stage('Checkout Code') {
            steps {                 
                script {
                    git branch: 'main', credentialsId: '60358b75-147f-44df-a0d6-779ec22d3da1', url: 'git@github.com:Marwan-alanani/Weather-App.git'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t $IMAGE_NAME .'
                }
            }
        }
        
        stage('Push Docker Image to Dockerhub')
        {
            steps{
                script{
                    sh 'docker push $IMAGE_NAME'
                }
            }
        }
        
        stage('Run ansible playbook'){
            steps{
                script{
                    sh 'export ANSIBLE_HOST_KEY_CHECKING=False'
                    sh 'chmod 600 private_keys/m01_private_key'
                    sh 'chmod 600 private_keys/m02_private_key'
                    sh 'ansible-playbook -i inventory playbook.yml'
                }
            }
        }
        
        

    }
    
}


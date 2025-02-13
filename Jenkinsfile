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
                    sh 'ansible playbook -i inventory playbook.yml'
                }
            }
        }
        
        
        

    }

    post {
        always {
            script {
                sh 'docker ps -a | grep $CONTAINER_NAME'
            }
        }
    }
}

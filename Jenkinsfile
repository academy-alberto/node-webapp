pipeline {
    agent {  
        label 'linux-node'  
    }  
    stages {
        stage('Checkout') {  
            steps {  
                git credentialsId: 'd92f3b5a-7de9-493a-9d95-c41448b1e9cd', url: 'https://github.com/aalberto/node-webapp.git', branch: 'main'
            }  
        }  
        stage('Build-Docker-Image') {
            steps {  
                script {  
                    docker.build('node-webapp:latest')
                }
            }  
        }  
        stage('Run-Docker-Container') {
            steps {  
                script {  
                    docker.image('node-webapp:latest').run('-d -p 3000:3000')
                }  
            }  
        }
    }  
}

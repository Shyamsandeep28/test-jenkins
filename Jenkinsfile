pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/Shyamsandeep28/Devops-project.git'
            }
        }
        
        stage('build') {
            steps {
                sh 'mvn clean'
                sh 'mvn package' 
            }
        }
        
        
        stage('deploy') {
            steps {
                sh 'docker build -t myappimage .'
                sh 'docker run -d --name application -p 8081:8080 myappimage'
            }
        }
        
    }
}


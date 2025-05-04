pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/nitinpadal/Ci-dc-practice.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t myapp-image .'
            }
        }
        
        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 9999:80 myapp-image'
            }
        }
    }
}

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
                script {
                    if (isUnix()) {
                        sh 'docker build -t myapp-image .'
                    } else {
                        bat 'docker build -t myapp-image .'
                    }
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'docker run -d -p 8080:8080 myapp-image'
                    } else {
                        bat 'docker run -d -p 8080:8080 myapp-image'
                    }
                }
            }
        }
    }
}

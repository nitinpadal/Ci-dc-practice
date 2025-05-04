pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/nitinpadal/Ci-dc-practice.git', branch: 'master'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("ci-dc-practice-image")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.run("-p 8080:80")
                }
            }
        }
    }
}

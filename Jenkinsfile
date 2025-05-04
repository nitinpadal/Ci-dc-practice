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

        stage('Stop Existing Container') {
            steps {
                script {
                    // Stop and remove any existing container using port 8080
                    bat '''
                    FOR /F "tokens=*" %%i IN ('docker ps -q --filter "ancestor=myapp-image"') DO docker stop %%i
                    '''
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker run -d -p 8080:80 myapp-image'
            }
        }
    }
}

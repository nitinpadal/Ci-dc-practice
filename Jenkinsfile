pipeline {
    agent any

    stages {
        stage('Cleanup and Stop Containers') {
            steps {
                script {
                    // Stop and remove any containers, networks, or volumes defined in docker-compose.yml
                    bat 'docker-compose down'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Start the container using docker-compose
                    bat 'docker-compose up -d'
                }
            }
        }
    }
}

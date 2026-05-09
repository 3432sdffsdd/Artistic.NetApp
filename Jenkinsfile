pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Docker Compose Build') {
            steps {
                sh 'docker compose-down'
                sh 'docker compose-up --build -d'
            }
        }

        stage('Check Containers') {
            steps {
                sh 'docker ps'
            }
        }
    }
}

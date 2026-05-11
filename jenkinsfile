pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Adirealsharma/Practical.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests...'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t cicd-demo .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker run -d -p 8081:80 cicd-demo'
            }
        }
    }
}

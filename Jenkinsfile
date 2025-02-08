pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/TodorBelchev/SeleniumIdeSoftUni'
            }
        }

        stage('Restore Dependencies') {
            steps {
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build the application') {
            steps {
                script {
                    bat 'dotnet build --no-restore'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    bat 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed!'
        }
    }
}
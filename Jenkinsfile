pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'dotnet build ./apiws/RESTApi/RESTApi.sln'
                
            }
        }
        stage('Test') {
            steps {
                // Specify each solution or test project file explicitly
                bat 'dotnet test ./apiws/RESTApi/RESTApi.sln'
                
            }
        }
        stage('Docker Build') {
            steps {
                bat 'docker-compose build'
            }
        }
        stage('Deploy') {
            steps {
                bat 'docker-compose up -d'
            }
        }
    }
}

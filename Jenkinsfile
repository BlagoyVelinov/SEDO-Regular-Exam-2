pipeline {
    agent any
    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Restore Dependencies of the project') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build the Horizons project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('Run Tests of the Horizons project') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
pipeline {
    agent any
    
    stages {
        stage('Hello') {
            steps {
                echo "Hello, World!"
            }
        }
        stage('Test Maven') {
            steps {
                sh """mvn -version"""
            }
        }
        stage('Checkout Git') {
            steps {
                echo "Pulling from git ...";
                    git branch: "main",
                    url: "https://github.com/khalilDimassi/TestDriveFreeStyle";
            }
        }
        stage('MVN CLEAN') {
            steps {
                sh "................."
            }
        }
        stage('MVN COMPILE') {
            steps {
                ""
            }
        }
        stage('MVN SONARQUBE') {
            steps {
                ""
            }
        }
    }
}

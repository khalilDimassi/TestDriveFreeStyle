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
        sh 'mvn clean'
      }
    }
    stage('MVN COMPILE') {
      steps {
        sh 'mvn compile'
      }
    }
    stage('MVN SONARQUBE') {
      steps {
        sh 'mvn sonar:sonar'
      }
    }
  }
}

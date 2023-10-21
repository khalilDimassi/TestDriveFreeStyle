pipeline {
  agent any
   
  stages {
    stage('Hello') {
      steps {
        echo 'Hello, World!'
      }
    }
    stage('Test Maven') {
      steps {
        sh """mvn -version"""
      }
    }
    stage('Checkout Git') {
      steps {
        echo 'Pulling from git ...';
          git branch: 'main',
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
    // stage('MVN SONARQUBE') {
    //    steps {
    //     withCredentials([string(credentialsId: 'sonar-token', variable: 'SONAR_TOKEN')]) {
    //       sh 'mvn sonar:sonar -Dsonar.login=$SONAR_TOKEN'
    //     }
    //   }
    // }
    stage('SCM') {
      checkout scm
    }
    stage('SonarQube Analysis') {
      def mvn = tool 'Default Maven';
      withSonarQubeEnv() {
        sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=TestDriveFreeStyle -Dsonar.projectName='TestDriveFreeStyle'"
      }
    }
  }
}

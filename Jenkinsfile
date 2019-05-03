pipeline {
    agent any

    tools {
        maven "maven 3.6"
    }

    stages {
        stage('Build') {
           steps{
              // Run the maven build
              sh "mvn clean package"
           }
        }
        stage('Checkstyle') {
           steps{
              // Run the maven build with checkstyle
              sh "mvn clean package checkstyle:checkstyle"
           }
        }
    }
}

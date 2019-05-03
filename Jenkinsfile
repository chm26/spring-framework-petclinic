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
    }
}

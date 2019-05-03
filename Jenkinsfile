pipeline {
    agent any
    tools {
        maven "maven 3.6"
    }
    options {
        parallelsAlwaysFailFast()
    }
    stages {
        stage('Non-Parallel Stage') {
            steps {
                echo 'This stage will be executed first.'
            }
        }
        stage('Parallel Stage') {
            parallel {
                   stage('Checkstyle') {
                        steps{
                            // Run the maven build with checkstyle
                            sh "mvn clean package checkstyle:checkstyle"
                         }
                     }
                    stage('Sonarqube') {
                        steps {
                            withSonarQubeEnv('SonarQube') {
                            sh "mvn  clean package sonar:sonar -Dsonar.host_url=$SONAR_HOST_URL "
                            echo "sonar en petclinic"
                            }
                         }
                    }
            }
        }
    }
}

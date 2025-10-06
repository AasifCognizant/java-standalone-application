pipeline {
    agent any

    tools {
        // These must match names configured in Jenkins > Global Tool Configuration
        jdk 'JDK22'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/AasifCognizant/java-standalone-application.git', branch: 'main'
            }
        }
        stage('Build') {
            steps {
                bat 'echo mvn clean install'
            }
        }
    }
}

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
                bat 'mvn clean install'
            }
        }

        stage('Run Application') {
            steps {
                bat 'java -jar target/java-standalone-application-1.0-SNAPSHOT.jar'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}

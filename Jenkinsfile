pipeline {
    agent any

    tools {
        jdk 'JDK17'
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                // Replace with your Git repository URL
                git url: 'https://github.com/AasifCognizant/java-standalone-application.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Run Application') {
            steps {
                // If you have a run command, add it here
                // Example: sh 'java -jar target/your-app.jar'
                echo 'Running application...'
            }
        }

        stage('Test') {
            steps {
                // This assumes tests are run during the build phase
                // If separate, use: sh 'mvn test'
                echo 'Tests executed during build phase'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}

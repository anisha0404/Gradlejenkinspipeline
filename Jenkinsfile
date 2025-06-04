pipeline {
    agent any  // Use any available agent

    tools {
        gradle 'gradle'  // Ensure this matches the name configured in Jenkins
        jdk 'JDK'
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/anisha0404/Gradlejenkinspipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle build'  // Run Maven build
            }
        }

       stage('Test') {
           steps {
               sh 'gradle test'  // Run unit tests
           }
        }

              
        stage('Run Application') {
            steps {
                // Start the JAR application
                sh 'gradle run'
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

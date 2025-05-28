pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Make sure this matches the Maven tool name in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Akashmishra1421/MyMavenJenkinsPipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenJenkinsPipeline-1.0-SNAPSHOT.jar'  // Run the jar
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


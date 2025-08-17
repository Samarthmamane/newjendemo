pipeline {
    agent any  // Run on any available agent

    environment {
        // Define environment variables
        MAVEN_HOME = '/usr/share/maven'
    }

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/your-user/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying application...'
                // Add deploy script or command
            }
        }
    }

    post {
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

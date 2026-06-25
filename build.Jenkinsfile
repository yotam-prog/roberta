pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }
      stage('Push to Docker Hub') {
    steps {
        script {
            // Leave the URL empty or use 'https://index.docker.io/v1/' for Docker Hub
            docker.withRegistry('', 'dockerhub-credentials-id') {
                def myImage = docker.build("username/my-app:latest")
                myImage.push()
            }
        }
    }
}
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // Add test commands here, e.g., sh 'pytest'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline has finished execution.'
        }
    }
}

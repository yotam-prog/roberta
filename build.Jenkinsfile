pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                // Typically you'd use checkout scm here
            }
        }

        stage('Docker Build & Push') {
            steps {
                script {
                    // If pushing to Docker Hub, use 'https://index.docker.io/v1/'
                    // Replace 'docker-hub-credentials' with the ID you created in Jenkins
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        
                        // 1. Build the image
                        def customImage = docker.build("yota45/my-image-name:${env.BUILD_NUMBER}")
                        
                        // 2. Push the image
                        customImage.push()
                        
                        // Optional: also push as 'latest'
                        customImage.push('latest')
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

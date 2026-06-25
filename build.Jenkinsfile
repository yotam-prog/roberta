pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
            }
        }
        stage('Build') {
            steps {
                echo 'Building your RoBERTa model/application...'
                // Add your build commands here, e.g., sh 'python setup.py build'
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

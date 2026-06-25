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
       sh '''
            docker login yotam2012@gmail.com
            docker build 1.0
            docker tag test
            docker push test push
       '''
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

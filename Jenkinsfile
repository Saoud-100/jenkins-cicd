pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing the application...'
                bat 'if exist index.html (echo Test passed: index.html exists) else (echo Test failed & exit /b 1)'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                bat 'if not exist deployment mkdir deployment'
                bat 'copy /Y index.html deployment\\index.html'
                echo 'Application deployed successfully!'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
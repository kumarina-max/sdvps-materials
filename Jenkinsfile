pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/kumarina-max/sdvps-materials.git'
            }
        }
        
        stage('Test') {
            steps {
                sh 'go test .'
            }
        }
        
        stage('Build') {
            steps {
                sh 'docker build . -t sdvps-app:latest'
            }
        }
    }
    
    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed!'
        }
    }
}

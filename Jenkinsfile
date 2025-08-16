pipeline {
    agent any

    stages {
        stage('Build Project') {
            steps {
                echo 'Building the project...'
                bat 'echo Build Successful'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'echo Running Tests...'
            }
        }
    }
    post {
        failure {
            echo "❌ Build failed. Check logs."
        }
        success {
            echo "✅ Build successful!"
        }
    }
}

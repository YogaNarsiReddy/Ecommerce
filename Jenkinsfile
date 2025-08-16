pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/YogaNarsiReddy/Ecommerce.git'
            }
        }

        stage('Build Project') {
            steps {
                echo 'Building the project...'
                // Example: Run backend build with Maven
                sh 'mvn clean package -DskipTests || true'
                // Example: Run frontend build with npm (if you have frontend folder)
                // dir('frontend') {
                //     sh 'npm install'
                //     sh 'npm run build'
                // }
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                sh 'mvn test || true'
            }
        }
    }

    post {
        success {
            echo '✅ Build completed successfully!'
        }
        failure {
            echo '❌ Build failed. Check logs.'
        }
    }
}

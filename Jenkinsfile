
pipeline {
    agent any

    environment {
        FLUTTER_HOME = 'C:\\Users\\moham\\OneDrive\\Desktop\\New folder\\flutter'
    }

    stages {
        stage('Configure Git') {
            steps {
                bat '''
                    git config --global --add safe.directory "C:/Users/moham/OneDrive/Desktop/New folder/flutter"
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '"%FLUTTER_HOME%\\bin\\flutter.bat" pub get'
            }
        }

        stage('Test') {
            steps {
                bat '"%FLUTTER_HOME%\\bin\\flutter.bat" test'
            }
        }

        stage('Build') {
            steps {
                bat '"%FLUTTER_HOME%\\bin\\flutter.bat" build web'
            }
        }

        stage('Archive Web Build') {
            steps {
                archiveArtifacts artifacts: 'build/web/**',
                    fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Flutter CI/CD pipeline successful!'
        }

        failure {
            echo 'Flutter CI/CD pipeline failed!'
        }
    }
}
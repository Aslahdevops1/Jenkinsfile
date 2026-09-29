
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Using the checked-out repository'
                bat 'git status'
            }
        }

        stage('Flutter Version') {
            steps {
                bat 'flutter --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }

        stage('Analyze') {
            steps {
                bat 'flutter analyze'
            }
        }

        stage('Test') {
            steps {
                bat 'flutter test'
            }
        }

        stage('Build APK') {
            steps {
                bat 'flutter build apk --release'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts:
                'build/app/outputs/flutter-apk/app-release.apk',
                fingerprint: true

            echo 'Flutter APK build successful!'
        }

        failure {
            echo 'Flutter CI/CD pipeline failed!'
        }
    }
}
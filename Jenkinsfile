
environment {
    FLUTTER_HOME = 'C:\\Users\\moham\\OneDrive\\Desktop\\New folder\\flutter'
    PATH = "${FLUTTER_HOME}\\bin;${env.PATH}"
}

stages {
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
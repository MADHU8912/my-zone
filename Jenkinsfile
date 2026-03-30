pipeline {
    agent any

    triggers {
        // Auto build every 5 minutes
        cron('H/5 * * * *')
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo '📥 Fetching code from GitHub...'
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Check Files (CMD)') {
            steps {
                echo '📂 Listing files using CMD...'
                bat 'dir'
            }
        }

        stage('Build') {
            steps {
                echo '⚙️ Running build...'
                bat 'echo Build started...'
                bat 'echo Jenkins CI/CD Build Success > build-log.txt'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running tests...'
                bat 'echo All tests passed'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying project...'
                bat 'echo Deployment done'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline SUCCESS'
        }
        failure {
            echo '❌ Pipeline FAILED'
        }
    }
}
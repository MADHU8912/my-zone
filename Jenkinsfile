pipeline {
    agent any

    triggers {
        cron('H/5 * * * *')
    }

    stages {
        stage('Check Files (CMD)') {
            steps {
                echo 'Checking files in workspace...'
                bat 'dir'
            }
        }

        stage('Build') {
            steps {
                echo 'Running build...'
                bat 'echo Build started...'
                bat 'echo Jenkins CI/CD Build Success > build-log.txt'
                bat 'type build-log.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying project...'
                bat 'echo Deployment done'
            }
        }
    }

    post {
        success {
            echo 'Pipeline SUCCESS'
        }
        failure {
            echo 'Pipeline FAILED'
        }
    }
}
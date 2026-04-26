pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Cloning repo..."
                git 'https://github.com/vvce23ise0101-eng/slack-demo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                bat 'echo BUILD SUCCESS'
            }
        }

        stage('Test') {
            steps {
                echo "Testing project..."
                bat 'echo TEST PASSED'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying..."
                bat 'echo DEPLOY SUCCESS'
            }
        }

        stage('Slack Notification') {
            steps {
                bat '''
                echo Sending Slack message...

                curl -X POST -H "Content-type: application/json" ^
                --data "{\"text\":\"🚀 Jenkins SUCCESS: slack-demo build #${BUILD_NUMBER} completed successfully\"}" ^
                echo "Slack notification executed"
                '''
            }
        }
    }

    post {
        always {
            echo "Pipeline completed"
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }

        stage('Notify Slack') {
            steps {
                bat '''
                curl -X POST -H "Content-type: application/json" ^
                --data "{\"text\":\"✅ Jenkins Build SUCCESS: slack-pakka #${BUILD_NUMBER}\"}" ^
                https://hooks.slack.com/services/YOUR/WEBHOOK/URL
                '''
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building project...'
            }
        }
    }

    post {
        success {
            script {
                slackSend(
                    channel: '#slack-pakka',
                    message: "✅ BUILD SUCCESS for ${env.JOB_NAME} #${env.BUILD_NUMBER}"
                )
            }
        }

        failure {
            script {
                slackSend(
                    channel: '#slack-pakka',
                    message: "❌ BUILD FAILED for ${env.JOB_NAME}"
                )
            }
        }
    }
}
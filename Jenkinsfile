pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
               sh "cat ./note.txt"
            }
        }
    }

    post {
        always {
            emailext attachLog: true, body: '''$PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS:
            Check console output at $BUILD_URL to view the results.''', recipientProviders: [developers()], subject: '$PROJECT_NAME - Build # $BUILD_NUMBER - $BUILD_STATUS!'
        }
    }
}

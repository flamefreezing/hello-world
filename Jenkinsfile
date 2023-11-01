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
      success {
            mail to: "angelinmyheart.98@gmail.com",
            subject: "[${env.BUILD_NUMBER}] - ${env.JOB_NAME} - ${currentBuild.result}",
            body: "OK",
      }
    }
}

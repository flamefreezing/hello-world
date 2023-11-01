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
        emailext(
            to: "duong.chieu.nguyen98@gmail.com, angelinmyheart.98@gmail.com",
            subject: "[${env.BUILD_NUMBER}] - ${env.JOB_NAME} - ${currentBuild.result}",
            body: "OK",
            attachLog: true
        )
      }
    }
}

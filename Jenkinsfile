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
            to: "angelinmyheart.98@gmail.com",
            from: "flamefreezingg@gmail.com",
            subject: "[${env.BUILD_NUMBER}] - ${env.JOB_NAME} - ${currentBuild.result}",
            body: "OK",
            attachLog: true
        )
      }
    }
}

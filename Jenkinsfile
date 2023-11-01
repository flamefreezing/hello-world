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
        mail to: "duong.chieu.nguyen98@gmail.com, angelinmyheart.98@gmail.com",
        subject: "#${env.BUILD_ID} - ${env.JOB_NAME} - ${currentBuild.result}",
        body: "${JELLY_SCRIPT,template="foobar"}",
        mimeType: "text/html"
        }
    }
}

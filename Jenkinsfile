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
        subject: "[${env.BUILD_NUMBER}] - ${env.JOB_NAME} - ${currentBuild.result}",
        body: '''<html>
                    <body>
                        <p>Result: <strong>${currentBuild.result}</strong></p>
                        <p>For further information, please refer to <a href="${env.BUILD_URL}">here</a></p>
                    </body>
              </html>'''
        ,
        attachLog: true
      }
    }
}

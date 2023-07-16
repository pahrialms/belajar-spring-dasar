pipeline {
    agent { label 'node-dev' }
    environment {
        AUTHOR = "Pahrial MS"
    }

    stages {
        stage('Parameter') {
          input {
            message "Can we deploy ?"
            ok "Yes, Of course"
            submitter "pahr"
          }
            steps {
                script {
                    for (int i = 0; i < 10; i++)
                    echo("Script ${i}")
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
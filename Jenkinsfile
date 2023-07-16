pipeline {
    agent { label 'node-dev' }
    environment {
        AUTHOR = "Pahrial MS"
    }
    parameters {
        string(name: "NAME", defaultValue: "Guest", description: "What is your name?")
        text(name: "DESCRIPTION", defaultValue: "Guest", description: "What is your name?")
        booleanParam(name: "DEPLOY", defaultValue: "false", description: "Need to deploy?")
        choice(name: "SOSMED", choices: ['Facebook', 'Twitter', 'Instagram'], description: "What is your sosmed" )
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'A secret password')
    }

    stages {
        stage('Preparation') {
          input {
            message "Can we deploy ?"
            ok "Yes, Of course"
            submitter "pahr"
          }
          steps {
              script {
                 echo "Hello ${env.AUTHOR}"
                 echo "Hello ${params.NAME}"
                 echo "Hello ${params.DESCRIPTION}"
                 echo "Hello ${params.DEPLOY}"
                 echo "Hello ${params.SOSMED}"
                 echo "Fill your password here ${params.PASSWORD}"
              }
          }
        }
        stage('Build') {
            steps {
            withCredentials([usernamePassword(
                credentialsId: "pahrial_rahasia",
                usernameVariable: "USER",
                passwordVariable: "PASSWORD"
            )]) {
             sh('echo "Releasae it with -u $USER -p $PASSWORD" > "release.txt"')
            }
            }

        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}
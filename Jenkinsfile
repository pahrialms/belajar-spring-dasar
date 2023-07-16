pipeline {
    agent { label 'node-dev' }
    environment {
        AUTHOR = "Pahrial MS"
    }
    parameters (
        string(name: "NAME", defaultValue: "Guest", description: "What is your name")
        text(name: "DESCRIPTION", defaultValue: "Guest", description: "What is your name")
        booleanParam(name: "DEPLOY", defaultValue: "false", description: "Need to deploy?")
    )

    stages {
        stage('Parameter') {
            steps {
                script {
                    for (int i = 0; i < 10; i++)
                    echo("Script ${i}")
                }
                echo "Hello ${env.AUTHOR}"
                echo "Hello ${params.NAME}"
                echo "Hello ${params.DESCRIPTION}"
                echo "Hello ${params.DEPLOY}"
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}

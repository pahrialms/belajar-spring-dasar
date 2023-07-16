pipeline {
    agent { label 'node-dev' }

    stages {
        stage('Test') {
            steps {
            script {
                for (int i = 0; i < 10; i++)
                    echo(Script ${i})
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

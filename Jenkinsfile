pipeline {
    agent { label 'node-dev' }

    stages {
        stage('Test') {
            steps {
                echo 'Hello Test'
                sh ("apt update -y")
                sh ("apt install net-tools -y")
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}

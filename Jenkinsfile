pipeline {
    agent { label 'node-dev' }

    stages {
        stage('Test') {
            steps {
                echo 'Hello Test'
            }
        }
        stage('Dev') {
            step {
                echo 'Hello Dev'
            }
        }
        stage('Pro') {
            steps {
                echo 'Hello Pro'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}

pipeline {
    agent { label 'node-dev' }

    stages {
        stage('Test') {
            steps {
                echo 'Hello Test'
                sh ("apt update -y")
                sh ("apt purge golang-go && apt autoremove")
                sh ("rm -rf $HOME/go")
                sh ("wget https://go.dev/dl/go1.18.3.linux-amd64.tar.gz")
                sh ("tar xvf go1.18.3.linux-amd64.tar.gz && chown -R root:root ./go")
                sh ("rm -rf /usr/local/go")
                sh ("mv go /usr/local")
                sh ('echo "export GOPATH=$HOME/work" >> ~/.profile')
                sh ('echo "export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin" >> ~/.profile')
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}

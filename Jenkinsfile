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
                sh ("rm -f /usr/local/go")
                sh ("mv go /usr/local")
                sh '''
                    cat <<EOF>> ~/.profile
                    export GOPATH=$HOME/work
                    export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
                    EOF
                ENDSSH'
                    '''
                sh ("source ~/.profile")
                sh ("go version")
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
    }
}

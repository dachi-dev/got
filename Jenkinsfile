pipeline {
    agent any
    triggers {
        githubPullRequest()
    }
    environment {
        // The API key will be injected as SOCKET_SECURITY_API_KEY
    }
    stages {
        stage('Socket Scan') {
            when {
                changeRequest target: 'main'
            }
            steps {
                script {
                    withCredentials([string(credentialsId: 'SOCKET-API', variable: 'SOCKET_SECURITY_API_KEY')]) {
                        sh '''
                            python3 -m venv .venv
                            PATH=.venv/bin:$PATH
                            pip install socketsecurity --upgrade
                            socketcli --target_path .
                        '''
                    }
                }
            }
        }
    }
} 
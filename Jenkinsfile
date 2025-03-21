pipeline {
    agent any

    environment {
        SERVER_CREDS = credentials('server-creds')
    }

    stages {

        stage('Setup') {
            
            steps {
                echo "my creds: ${SERVER_CREDS}"
                echo "Username: ${SERVER_CREDS_USR}"
                echo "Password: ${SERVER_CREDS_PSW}"
                sh "pip3 install --break-system-packages -r requirements.txt"
            }
        }

        stage('Test') {
            steps {
                sh 'export PATH=$HOME/.local/bin:$PATH && pytest test_app.py'
            }
        }
    }
}

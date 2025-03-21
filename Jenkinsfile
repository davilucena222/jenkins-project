pipeline {
    agent any

    environment {
        DB_HOST = '192.168.12.1'
        USERNAME = 'user1'
        PASSWORD = 'password123'
    }

    stages {

        stage('Setup') {
            steps {
                sh "pip3 install --break-system-packages -r requirements.txt"
                echo "The database IP is: ${DB_HOST}"
            }
        }

        stage('Test') {
            steps {
                sh 'export PATH=$HOME/.local/bin:$PATH && pytest test_app.py'
                echo "The DB username is: ${USERNAME} and the password is: ${PASSWORD}"
            }
        }
    }
}

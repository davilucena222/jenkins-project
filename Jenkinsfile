pipeline {
    agent any

    options {
        timeout(time: 1, unit: 'MINUTES')
    }

    stages {
        stage('lint and format') {
            steps {
                sh "sleep 70"
            }
        }

        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'server-creds', usernameVariable: "myuser", passwordVariable: "mypassword")]) {
                    sh '''
                        echo ${myuser}
                        echo ${mypassword}
                    '''
                }

                sh "pip install --break-system-packages -r requirements.txt"
            }
        }

        stage('Test') {
            steps {
                sh 'export PATH=$HOME/.local/bin:$PATH && pytest test_app.py'
            }
        }
    }
}

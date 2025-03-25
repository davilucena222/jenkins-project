pipeline {
    agent any

    stages {

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

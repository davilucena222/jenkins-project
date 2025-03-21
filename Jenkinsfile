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
            }
        }

        stage('Test') {
            steps {
                sh 'export PATH=$HOME/.local/bin:$PATH && pytest test_app.py'
            }
        }
    }
}

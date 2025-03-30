pipeline {
    agent any 

    stages {
        stage("Lint and Format") {
            parallel {
                stage("linting") {
                    steps {
                        sh "sleep 30"
                    }
                }

                stage("formatting") {
                    steps {
                        sh "sleep 30"
                    }
                }
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

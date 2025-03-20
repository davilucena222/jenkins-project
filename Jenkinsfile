pipeline {
    agent any
    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/davilucena222/jenkins-project.git', branch: 'main'
                sh "ls -ltr"
            }
        }

        stage('Setup') {
            steps {
                sh "pip3 install --break-system-packages -r requirements.txt"
            }
        }

        stage('Test') {
            steps {
                script {
                    sh "pytest"
                }
            }
        }
    }
}

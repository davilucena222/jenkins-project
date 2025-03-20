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
                script {
                    sh "apt-get install -y python3 python3-pip python3-venv"
                    sh "python3 -m venv venv"
                    sh "source venv/bin/activate && pip install -r requirements.txt"
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh "source venv/bin/activate && pytest"
                }
            }
        }
    }
}

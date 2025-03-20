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
                    sh "pip install -r requirements.txt"
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

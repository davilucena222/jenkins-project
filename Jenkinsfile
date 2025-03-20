pipeline {
    agent any
    environment {
        IMAGE_NAME = 'sanjeevkt720/jenkins-flask-app'
        IMAGE_TAG = "${IMAGE_NAME}:${env.BUILD_NUMBER}"
        KUBECONFIG = credentials('kubeconfig-credentials-id')

    }
    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/davilucena222/jenkins-project.git', branch: 'main'
                sh "ls -ltr"
            }
        }
        stage('Setup') {
            steps {
                sh "pip install -r requirements.txt"
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                sh "whoami"
            }
        }
    }
}

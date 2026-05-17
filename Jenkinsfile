pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'url: 'https://github.com/lakshmipriyayadav/Poc-19-branching-cicd.git''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t poc19-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh '''
                docker stop poc19-container || true
                docker rm poc19-container || true

                docker run -d -p 5001:5000 --name poc19-container poc19-app
                '''
            }
        }

    }
}

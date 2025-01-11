pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-web-app .'
            }
        }
        stage('Test') {
            steps {
                sh 'docker run -p 8080:80 my-web-app'
                sh 'curl http://localhost:8080'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker tag my-web-app:latest techysurinder/my-web-app:latest'
                sh 'docker push techysurinder/my-web-app:latest'
            }
        }
    }
}

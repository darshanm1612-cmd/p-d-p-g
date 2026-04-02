pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t python-app .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker stop python-app || true'
                sh 'docker rm python-app || true'
                sh 'docker run -d -p 5000:5000 --name python-app python-app'
            }
        }
    }
}

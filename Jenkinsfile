pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker build -t python-app .'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker stop python-app || exit 0'
                bat 'docker rm python-app || exit 0'
                bat 'docker run -d -p 5001:5000 --name python-app python-app'
            }
        }
    }
}

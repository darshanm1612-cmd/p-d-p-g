pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/darshanm1612-cmd/p-d-p-g.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t python-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f python-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name python-container python-app'
            }
        }

    }
}

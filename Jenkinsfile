pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/darshanm1612-cmd/p-d-p-g.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t python-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker rm -f python-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5000:5000 --name python-container python-app'
            }
        }

    }
}

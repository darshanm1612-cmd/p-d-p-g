pipeline {
pipeline {
    agent any

    environment {
        IMAGE_NAME = "darshan1612/python-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main', url: 'https://github.com/darshanm1612-cmd/p-d-p-g.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t %IMAGE_NAME% .'
            }
        }

        stage('Tag Image') {
            steps {
                bat 'docker tag %IMAGE_NAME% %IMAGE_NAME%:latest'
            }
        }

        stage('Push to DockerHub') {
            steps {
                bat 'docker push %IMAGE_NAME%:latest'
            }
        }

        stage('Stop Old Container') {
            steps {
                bat 'docker rm -f python-container || exit 0'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 5001:5000 --name python-container %IMAGE_NAME%:latest'
            }
        }

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

pipeline {
    agent any

    environment {
        APP_NAME = "myapp"
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/donepriyanka99/nodejs-app1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:3000 myapp'
            }
        }
    }
}

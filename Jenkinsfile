pipeline {
    agent any

    environment {
        APP_NAME = "nodejs-app1"
    }

    stages {

        stage('Clone Code') {
            steps {
                echo "Cloning GitHub Repository"

                git branch: 'main',
                url: 'https://github.com/donepriyanka99/nodejs-app1.git'
            }
        }

        stage('Workspace Check') {
            steps {
                echo "Checking Workspace Files"

                sh 'pwd'
                sh 'ls -la'
            }
        }

        stage('Build') {
            steps {
                echo "Starting Build Process"

                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo "Running Application Tests"

                sh 'node app.js'
            }
        }

        stage('Package') {
            steps {
                echo "Packaging Application"

                sh 'tar -czf nodejs-app.tar.gz *'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploy Stage Started"

                sh 'echo Application Deployed Successfully'
            }
        }

    }

    post {

        always {
            echo "Pipeline Execution Completed"
        }

        success {
            echo "Pipeline Executed Successfully"
        }

        failure {
            echo "Pipeline Failed"
        }
    }
}

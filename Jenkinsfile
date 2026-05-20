pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'pip3 install -r requirements.txt --break-system-packages'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 -m pytest tests/ -v'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying app..."'
            }
        }
    }

    post {
        success { echo 'Pipeline passed!' }
        failure { echo 'Pipeline failed!' }
    }
}

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'pytest tests/ -v'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying app..."'
                sh 'python app.py || true'
            }
        }
    }

    post {
        success { echo 'Pipeline passed!' }
        failure { echo 'Pipeline failed!' }
    }
}

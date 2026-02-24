pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo "Repository already checked out by Jenkins"
            }
        }

        stage('Setup Python') {
            steps {
                bat '''
                python --version
                python -m venv venv
                call venv\\Scripts\\activate
                pip install -r requirements.txt
                '''
            }
        }

        stage('Run Script') {
            steps {
                bat '''
                call venv\\Scripts\\activate
                python app.py
                '''
            }
        }
    }
}
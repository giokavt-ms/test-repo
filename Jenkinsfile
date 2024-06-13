pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/giokavt-ms/test-repo.git", branch: "master"
            }
        }

         stage('Setup Python') {
            steps {
                sh 'sudo apt install python3.12-venv -y'
            }
        }
        
        stage('Setup Python Environment') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate'
                sh 'pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the django application'
                sh '. venv/bin/activate && nohup python3 manage.py runserver 0.0.0.0:8000 &'
            }
        }
    }
}

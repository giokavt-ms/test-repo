pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/giokavt-ms/test-repo.git", branch: "master"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the django application'
                sh 'sudo systemctl restart django.service'
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage("Clone Code") {
            steps {
                echo "Cloning the code"
                git url: "https://github.com/giokavt-ms/test-repo.git", branch: "master"
            }
        }
        stage("Deploy") {
            steps {
                echo "Deploying the django application"
                sh "python3 manage.py runserver 0.0.0.0:8000 &"
            }
        }
        }
    }

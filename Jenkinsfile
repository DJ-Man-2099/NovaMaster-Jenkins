pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                // Checkout code from GitHub
                git url: 'https://github.com/MariaGeorge22/NovaMaster-Jenkins.git', branch: 'main'
            }
        }
        stage("Run App") {
            steps {
                bat "pip install -r requirements.txt"
                bat "python manage.py runserver"
            }
        }
    }
}

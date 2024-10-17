pipeline {
    agent any

    environment {
        IMAGE_NAME = 'novaverse-jenkins'  // Replace with your Docker image name
    }

    stages {
        stage('Clone repository') {
            steps {
                // Checkout code from GitHub
                git url: 'https://github.com/MariaGeorge22/NovaMaster-Jenkins.git', branch: 'main'
            }
        }
        stage("Run App") {
            steps {
                sh "pip install -r requirements.txt"
                sh "python manage.py runserver"
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean workspace after the build
        }
    }
}

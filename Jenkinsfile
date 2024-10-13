pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                // Checkout code from GitHub
                git url: 'https://github.com/MariaGeorge22/CI-CD.git', branch: 'main'
            }
        }
        stage("Run App") {
            steps {
                bat "dir"
            }
        }
    }
}

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
        stage("Build App") {
            steps {
             script {
                    // Build the Docker image
                    def image = docker.build("novamaster-jenkins:${env.BUILD_ID}") // Change "myapp" to your image name
                }
            }
        }
        stage("Run App") {
            steps {
              script {
                    // Run the Docker container
                    docker.image("novamaster-jenkins:${env.BUILD_ID}").inside {
                        // Commands to execute inside the container
                        sh 'echo "Running inside the Docker container"'
                    }
                }
            }
        }
    }

    post {
        always {
            cleanWs()  // Clean workspace after the build
        }
    }
}

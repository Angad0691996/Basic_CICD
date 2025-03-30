pipeline {
    agent any

    environment {
        PYTHON_VERSION = 'python3'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-credentials', url: 'https://github.com/Angad0691996/Basic_CICD.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'echo "jenkins ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/jenkins' // Ensures passwordless sudo
                sh 'sudo apt update && sudo apt install -y python3 python3-pip'
            }
        }

        stage('Run Python Script') {
            steps {
                sh '${PYTHON_VERSION} app.py'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}

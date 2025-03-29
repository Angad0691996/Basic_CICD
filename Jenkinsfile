pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git credentialsId: 'github-credentials', url: 'https://github.com/Angad0691996/Basic_CICD.git', branch: 'main'
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    sh 'python3 app.py'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

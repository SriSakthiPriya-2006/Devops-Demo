pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Fetching source code...'
                git branch: 'main', url: 'https://github.com/SriSakthiPriya-2006/Devops-Demo/new/main'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed for static frontend files.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Archiving static files for deployment...'
                archiveArtifacts artifacts: '**/*', onlyIfSuccessful: true
            }
        }
    }

    post {
        success {
            echo 'Frontend pipeline completed successfully ✅'
        }
        failure {
            echo 'Pipeline failed ❌'
        }
    }
}

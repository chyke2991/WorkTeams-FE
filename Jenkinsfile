pipeline {
    agent any
    tools {
        nodejs 'Node24' // Assumes NodeJS plugin with 'Node16' installation configured
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/chyke2991/WorkTeams-FE.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
       
    }
    post {
        always {
            cleanWs()
        }
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

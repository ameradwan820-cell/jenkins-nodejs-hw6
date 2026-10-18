pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ameradwan820-cell/jenkins-nodejs-hw6.git'
            }
        }

        stage('Build') {
            steps {
                sh 'node --version'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'dist/**', fingerprint: true
        }
    }
}

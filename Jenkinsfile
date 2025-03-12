pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/dpei0287/jenkins-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t jenkins-demo .'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'docker run -d -p 3000:80 --name apache-container jenkins-demo'
                }
            }
        }

        stage('Test Deployment') {
            steps {
                script {
                    sh 'curl -I http://localhost:3000'
                }
            }
        }
    }
}

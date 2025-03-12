pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Clone the public GitHub repository
                    checkout([
                        $class: 'GitSCM', 
                        branches: [[name: '*/main']], 
                        userRemoteConfigs: [[url: 'https://github.com/dpei0287/jenkins-demo.git']]
                    ])
                }
            }
        }
        
        stage('List Files') {
            steps {
                script {
                    sh 'ls -la'
                    sh 'pwd'
                    sh 'hostname'
                }
            }
        }
    }
}

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
                        userRemoteConfigs: [[url: 'https://github.com/jared-codes/demo-repo.git']]
                    ])
                }
            }
        }
        
        stage('List Files') {
            steps {
                script {
                    sh 'ls -la'
                }
            }
        }
    }
}

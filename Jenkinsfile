pipeline {
    agent any

    environment {
        REPO_OWNER = 'dpei0287'
        REPO_NAME = 'jenkins-demo'
    }

    stages {
        stage('Close GitHub Repository') {
            steps {
                script {
                    def response = sh(script: """
                        curl -X PATCH \
                        -H \"Accept: application/vnd.github.v3+json\" \
                        https://api.github.com/repos/$REPO_OWNER/$REPO_NAME \
                        -d '{"archived": true}'
                    """, returnStdout: true).trim()
                    
                    echo "GitHub API Response: ${response}"
                }
            }
        }
    }
}

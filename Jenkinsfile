pipeline {
    agent any

    stages {
        stage("Restore project dependencies") {
            steps {
                sh 'dotnet restore'
            }
        }
        
        stage("Build the project") {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
    
        post {
            always {
                cleanWs()
            }
            success {
                echo 'Pipeline succeeded!'
            }
            failure {
                echo 'Pipeline failed!'
            }
        }
    }
}
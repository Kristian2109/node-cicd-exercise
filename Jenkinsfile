pipeline {
    agent any
    tools {
        nodejs 'Node JS Latest'
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }
    }
}
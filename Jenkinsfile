pipeline {
    agent any
    tools {
        nodejs 'Node JS Latest'
    }

    stages {
        stage('Build adn Run') {
            steps {
                script {
                    sh 'npm install & node app.js'
                }
            }
        }

        stage('Publish') {
            steps {
                script {
                    sh '''
                    new_image_name=kristian2109/cicd:${git rev-parse HEAD}
                    docker build -t ${new_image_name} .
                    docker push ${new_image_name}
                    docker rmi ${new_image_name}
                    '''
                }
            }
        }
    }
}
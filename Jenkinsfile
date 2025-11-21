pipeline {
    agent any

    environment {
        DOCKER_CREDS = credentials('dockerhub') // only DockerHub credentials
    }

    stages {

        stage('Checkout Code') {
            steps {
                // Public repo does not require credentials
                git branch: 'main',
                    url: 'https://github.com/barathh1357/react_app.git'
            }
        }

        stage('Change File Permissions') {
            steps {
                sh 'chmod +x build.sh'
            }
        }

        stage('Build & Deploy Docker') {
            steps {
                sh """
                    export DOCKER_USERNAME="${DOCKER_CREDS_USR}"
                    export DOCKER_PASS="${DOCKER_CREDS_PSW}"
                    ./build.sh
                """
            }
        }
    }

    post {
        success { echo 'Pipeline finished successfully!' }
        failure { echo 'Pipeline failed. Check logs.' }
    }
}

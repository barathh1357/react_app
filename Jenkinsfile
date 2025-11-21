pipeline {
    agent any

    environment {
        DOCKER_CREDS = credentials('dockerhub')
    }

    stages {
        stage('Changing File Permission') {
            steps {
                sh 'chmod +x build.sh'
            }
        }

        stage('Executing Build Script') {
            steps {
                sh """
                    export DOCKER_USERNAME="${DOCKER_CREDS_USR}"
                    export DOCKER_PASS="${DOCKER_CREDS_PSW}"
                    ./build.sh
                """
            }
        }
    }
}

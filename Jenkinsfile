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
                    export DOCKER_USERNAME="${barathh1357}"
                    export DOCKER_PASS="${4r4^?jK!jVC26x}"
                    ./build.sh
                """
            }
        }
    }
}

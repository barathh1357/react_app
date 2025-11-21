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
                    export DOCKER_USERNAME=${barathh1357}
                    export DOCKER_PASS=${dckr_pat_sWb5ji1wtXsnaYvznBTDpR9vwcE}
                    ./build.sh
                """
            }
        }
    }
}

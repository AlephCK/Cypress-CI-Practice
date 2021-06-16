pipeline {
    agent any
    tools {nodejs "node"}

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Build') {
            steps {
                echo "Running build ${env.BUILD_ID} on ${env.JENKINS_URL}"
                sh 'npm ci'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'cypress run --spec cypress/integration/tests/*.js'
            }
        }
    }
}
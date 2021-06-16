pipeline {
    agent any

    tools {nodejs "node"}

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm i'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'cypress run --spec cypress/integration/tests/*.js'
            }
        }
    }
}
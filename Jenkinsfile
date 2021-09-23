pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'date'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('DeployDev') {
            when {
                branch 'development'
            }
            steps {
                echo 'Deploying to develop....'
            }
        }
        stage('DeployPROD') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to PROD....'
            }
        }
    }
}


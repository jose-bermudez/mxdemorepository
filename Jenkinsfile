pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'apt-get install htop'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }

        stage('DeployFeature') {
            when {
                branch pattern: "feature-\\d+", comparator: "REGEXP"
            }
            steps {
                echo 'Deploying feature....'
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


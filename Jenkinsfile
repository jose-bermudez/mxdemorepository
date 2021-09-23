pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'ls'
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
                echo 'Es una feature brancEs una feature branch'
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


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
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "jose-bermudez"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                echo 'Deploying to PROD....'
            }
        }
    }
}


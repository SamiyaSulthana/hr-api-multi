pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git url:"https://github.com/SamiyaSulthana/hr-api-multi", branch: "main"
            }
        }
        stage('Maven Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Dev Deploy') {
            when{
                branch 'develop'
            }
            steps {
                echo "deploy to dev environment"
            }
        }
        stage('QA Deploy') {
            when{
                branch 'qa'
            }
            steps {
                echo "deploy to qa environment"
            }
        }
        stage('prod Deploy') {
            when{
                branch 'main'
            }
            steps {
                echo "deploy to prod environment"
            }
        }
    }
}
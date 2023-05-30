pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Version') {
            steps {
                bat 'gradle --version'
            }
        }
        stage('Build') {
            steps {
                bat 'gradle assemble'
            }
        }
         stage('Test') {
            steps {
                bat 'gradle test'
            }
        }
        stage('Build Docker Image') {
            steps {
                bat 'gradle docker'
            }
        }
        stage('Run Docker Image') {
            steps {
                bat 'gradle dockerRun'
            }
        }
    }
}
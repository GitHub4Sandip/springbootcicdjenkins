pipeline {
    agent {label 'linux'}
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Version') {
            steps {
                sh 'gradle --version'
            }
        }
        stage('Build') {
            steps {
                sh 'gradle assemble'
            }
        }
         stage('Test') {
            steps {
                sh 'gradle test'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'gradle docker'
            }
        }
        stage('Run Docker Image') {
            steps {
                sh 'gradle dockerRun'
            }
        }
    }
}
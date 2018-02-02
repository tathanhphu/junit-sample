#!/usr/bin/env groovy

pipeline {
    agent {
        docker {
            image 'node'
            args '-u root'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test'
            }
        }
    }
    post {
        always { 
            steps{
                submitJunitToqTest([appSecretKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerId: 6223, containerType: 'release', createNewTestSuiteEveryBuild: true, eachMethodAsTestCase: false, environmentId: 0, overwriteExistingTestSteps: true, projectId: 3964, readFromJenkins: false, resultPattern: '', submitToContainer: true, url: 'https://sandbox.qtestdev.com'])
            }

        }
        success {
            echo 'Success'
        }
        failure {
            echo 'Failure'
        }
    }
}

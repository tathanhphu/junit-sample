#!/usr/bin/env groovy

pipeline {
   agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                bash 'mvn test'
            }
            post {
            always {
              sh 'This will always run'
            }
            failure {
              sh 'This will run only if failed'
            }
            changed {
              sh 'This will run only if the state of the Pipeline has changed')
            }
         }
        }
    }
    
}

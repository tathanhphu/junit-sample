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
				   echo 'Always'
				   submitJunitToqTest([appSecretKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', moduleId:999, containerId: 6223, containerType: 'release', createNewTestSuiteEveryBuild: true, eachMethodAsTestCase: false, environmentId: 0, overwriteExistingTestSteps: true, projectId: 3964, readFromJenkins: false, resultPattern: '', submitToContainer: true, url: 'https://sandbox.qtestdev.com'])
				   
				}
				success {
					echo 'Success'
				}
				failure {
					echo 'Failure'
				}
			}
        }
    }
    
}

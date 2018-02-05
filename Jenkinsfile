pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                //mvn 'test'
            }
			post {
				always {        
				   echo 'Always'
				   //submitJunitToqTest([appSecretKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerId: 6223, containerType: 'release', createNewTestSuiteEveryBuild: true, eachMethodAsTestCase: false, environmentId: 0, overwriteExistingTestSteps: true, projectId: 3964, readFromJenkins: false, resultPattern: '', submitToContainer: true, url: 'https://sandbox.qtestdev.com'])
				   submitJUnitTestResultsToqTest([apiKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerID: 12524, containerType: 'TEST-CYCLE', createNewTestRunsEveryBuildDate: false, createTestCaseForEachJUnitTestClass: false, environmentID: 0, overwriteExistingTestSteps: false, parseTestResultsFromTestingTools: false, parseTestResultsPattern: 'target/**/**.xml', projectID: 3964, qtestURL: 'https://sandbox.qtestdev.com', submitToExistingContainer: true])

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

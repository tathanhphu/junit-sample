pipeline {
    agent any
	tools { 
        maven 'maven3.3.9' 
        jdk 'java1.8.0_144' 
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                //sh "${maven}/bin/mvn test"
		bat "mvn test"
            }
        }
    }
	post {
		always {
		   echo 'Always'
		   echo "Post-Init result: ${currentBuild.result}"
                   echo "Post-Init currentResult: ${currentBuild.currentResult}"
		   echo "Get Current Result: ${currentBuild.getCurrentResult()}"
		   submitJUnitTestResultsToqTest([apiKey: '6a54dd8d-8f8a-4ac4-9673-6d05c2e5712f', containerID: 5787, containerType: 'release', createNewTestRunsEveryBuildDate: false, createTestCaseForEachJUnitTestClass: true, createTestCaseForEachJUnitTestMethod: false, overwriteExistingTestSteps: true, parseTestResultsFromTestingTools: true, projectID: 233, qtestURL: 'https://sandbox.qtestdev.com', submitToAReleaseAsSettingFromQtest: false, submitToExistingContainer: true, utilizeTestResultsFromCITool: false])


		}
		success {
			echo 'Success'
		}
		failure {
			echo 'Failure'
		}
	}    
}

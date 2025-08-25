pipeline {
	agent any
	stages {
  		stage('Build') {
   			steps {
    			echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
   			}
		}
  		stage('Test') {
   			steps {
    			echo "Test"
   			}
  		}
  		stage('Integration Test') {
   			steps {
    			echo "Integration Test"
   			}
		}
	} 
	post {
		always {
			echo "This will always run"
		}
		success {
			echo "This will run only if successful"
		}
		failure {
			echo "This will run only if failed"
		}
	}
}
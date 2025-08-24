pipeline {
	agent any
	stages {
  		stage('Build') {
   			steps {
				sh 'mvn --version'
    			echo "Build"
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
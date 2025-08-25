pipeline {
	agent any

	tools {
		maven 'myMaven'
		dockerTool 'myDocker'
	}

	// environment {
	// 	dockerHome = tool 'myDocker'
	// 	mavenHome = tool 'myMaven'
	// 	PATH = "${dockerHome}\\bin;${mavenHome}\\bin;${PATH}"
	// }

	stages {
  		stage('Checkout') {
   			steps {
				bat 'mvn --version'
				bat 'docker --version'
    			echo "Build"
				echo "$PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
   			}
		}
		stage('Compile') {
   			steps {
    			bat 'mvn clean compile'
   			}
  		}
  		stage('Test') {
   			steps {
    			bat 'mvn test'
   			}
  		}
  		stage('Integration Test') {
   			steps {
    			bat 'mvn failsafe:integration-test failsafe:verify' //used for integration tests
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
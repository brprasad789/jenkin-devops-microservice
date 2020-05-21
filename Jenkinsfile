//Scripted
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }
//Declarative
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:14.2'} }
	stages {
		stage ('Build') {
			steps {
				//sh 'maven --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}	
		stage ('Test') {
			steps {
				echo "Test"
			}
		}	
		stage ('Integration Test') {
			steps {
				echo "Test"
			}
		}
	}
	post {
		always {
			echo "Im awesome, I Run Always"
		}
		success {
			echo "I Run when u r successful"
		}
		failure {
			echo "I Run when u r failed"
		}
		
	}
}
//Scripted
// node {
// 	echo "Build"
// 	echo "Test"
// 	echo "Integration Test"
// }
//Declarative
pipeline {
	//agent any
	agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:14.2'} }
	stages {
		stage ('Build') {
			steps {
				//sh 'maven --version'
				echo "Build"
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
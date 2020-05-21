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
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}	
		stage ('Compile') {
			sh 'mvn clean compile'
		}

		stage ('Test') {
			steps {
				sh 'mvn test'
			}
		}	
		stage ('Integration Test') {
			steps {
				sh 'mvn failsafe:integration-test fail	safe:verify'
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
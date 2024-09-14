//Scripted
/*node {
	stage('Build') {
		echo "Build"
	}
	stage('Test') {
		echo "Test"
	}
}*/

//Declarative
pipeline {
	agent any
	//agent{docker{ image 'node:22-alpine3.19'}}
	stages{
		stage("Build"){
			steps{
				//sh "node --version"
				echo "Build"
				echo "BUILD_ID"
				echo "env.BUILD_ID"
				echo "BUILD_NUMBER"
				echo "env.BUILD_NUMBER"
				echo "JENKINS_URL"
				echo "env.JENKINS_URL"

			}
		}
		stage("Test"){
			steps{
				echo "Test"
			}
		}
		stage("Integration Test"){
			steps{
				echo "Integration Test"
			}
		}
	}
	post{
		always{
			echo "I run always"
		}
		success{
			echo "I run when pipeline succeeds"
		}
		failure{
			echo "I run when pipeline fails"
		}
		//changed{}
	}
}
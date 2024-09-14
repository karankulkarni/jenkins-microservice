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
	environment{
		dockerHome=tool 'firstDocker'
		mavenHome=tool 'firstMaven'
		PATH= "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage("Checkout"){
			steps{
				sh "mvn --version"
				sh "docker --version"
				echo "Build"
				echo "BUILD_ID"
				echo "$env.BUILD_ID"
				echo "BUILD_NUMBER"
				echo "$env.BUILD_NUMBER"
			}
		}
		stage("Complie"){
			steps{
				sh "mv clean compile"
			}
		}
		stage("Test"){
			steps{
				sh "mvn test"
			}
		}
		stage("Integration Test"){
			steps{
				sh "mvn failsafe:integration-test failsafe:verfiy"
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
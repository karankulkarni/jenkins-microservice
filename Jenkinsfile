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
	//agent any
	agent{
		docker{
			image 'maven:latest'
		}
	}
	stages{
		stage("Build"){
			steps{
				sh "mvn --version"
				echo "Build"
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
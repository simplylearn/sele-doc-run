pipeline{
	
	agent any 
	stages{
		stage("Start Grid"){
			steps{
				sh "docker-compose up -d hub chrome firefox"
			}



		}
		stage("Run test"){
			steps{

				sh "docker-compose up testng-module"
			}
		}
		
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"

		}
	}


}

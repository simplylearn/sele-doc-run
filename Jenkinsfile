pipeline{
	
	agent any 
	stages{
		stage("Pull latest Image"){
			steps{
				sh ' docker pull doc20001/selenium-dcoker'
			}

		}

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

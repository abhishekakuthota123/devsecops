#!groovy
pipeline {
	agent any 
	stages {
			
			stage('Build docker images') 
			{
      				steps {
        				sh 'docker build -t abhishekakuthota/mytag2 .'
      				      }
    			}

			stage("push")
			{
				steps
				{
				withDockerRegistry(credentialsId: 'DockerHub', url:"")
					{
					sh 'docker push abhishekakuthota/mytag2:latest'
					}
				}
			}

			stage('Trufflehog'){
    				steps{
    				sh 'docker run --name truffle abhishekakuthota/mytag2:latest --regex --entropy=False "https://github.com/dxa4481/truffleHog"|| true '
    				sh 'docker rm truffle || true'
    						}
   					}
     
							
		}
	}
			
		
	

		

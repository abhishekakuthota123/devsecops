#!groovy
pipeline {
	agent any 
	stages {
			stage("push")
			{
				steps
				{
				withDockerRegistry(credentialsId: 'DockerHub', url:"")
					{
					sh 'docker push abhishekakuthota/devsecops:mytag2'
					}
				}
			}
			stage('Execute Rundeck job') {
			      steps {
			 	 script {
			 	   step([$class: "RundeckNotifier",
  			           includeRundeckLogs: true,
			           jobId: "1394a8a5-2738-451a-b082-e589c4f77cd3",
        			   rundeckInstance: "rundeck",
          			   shouldFailTheBuild: true,
          			   shouldWaitForRundeckJob: true,
          			   tags: "",
          			   tailLog: true])
					}
				     }
							}
		}
	}
			
		
	

		

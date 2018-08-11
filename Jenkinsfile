pipeline {
	agent any
	
	stages{
		stage('Build'){
			
			steps{
				sh '/opt/maven/bin/mvn clean package'
		
			}
			post {
				success {  
					echo 'Now archiving...!'
					archiveArtifacts artifacts: '**/*.war'
				}
			}
		}
		stage('Deploy to Staging'){
				
			steps{
				build job: 'deploy-to-staging'
			}			
		}	
	
		
	
	}
}

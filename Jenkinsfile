pipeline {
	agent any

	stages {
		stage('Build'){
			steps{
				echo 'Building and Packaging ...'
				sh 'mvn clean package'
				echo 'Packaging done'
				}
			}
		
		stage('Deploying'){
			steps{
				echo 'Deploying to tomcat'
				sh 'scp  /var/lib/jenkins/workspace/PET_Clinic/target/petclinic.war  root@52.29.22.138:/opt/tomcat/webapps'
				echo 'Deployed'
				}
			}

		stage('Moving to Nexus'){
			steps{
				echo 'Moving to Nexus'
				}
			}
		
		stage('Process completed successfully'){
			steps{
				echo 'Completed successfully'
				}
			}
		}
	}

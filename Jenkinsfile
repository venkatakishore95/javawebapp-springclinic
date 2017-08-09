pipeline {
	
	agent any

	stages {
		stage('Building'){
			steps{
				
   				echo "JENKINS_HOME = ${env.JENKINS_HOME}"
   				echo "JOB_NAME = ${env.JOB_NAME}"
   
				echo 'Building and Packaging ...'
				sh 'mvn clean package'
				echo 'Packaging done'
				
				}
			}
		
		stage('Deploying'){
			steps{
				echo 'Deploying to tomcat'
				
				echo "JEN ==>${env.JENKINS_HOME} ... pjt ==> ${env.JOB_NAME} "
				sh "scp  ${env.JENKINS_HOME}/workspace/${env.JOB_NAME}/target/petclinic.war  root@52.29.22.138:/opt/tomcat/webapps"
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
		
		 /* stage('Sonarqube analysis') {
    steps {
    script {
             scannerHome = tool 'SonarScanner';
        }
     withSonarQubeEnv('SonarQube') {
         sh "${scannerHome}/bin/sonar-scanner.sh" 
    }

    }
        }*/
		
		
		}
	}

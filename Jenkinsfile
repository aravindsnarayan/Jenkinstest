pipeline {
	agent any
	
	stages {
		
		
	
		stage('Build') {
			steps {
				ws('/var/lib/tomcat7/webapps') { echo "Worspace changed "}
				echo "Building the checked-out project!";
				sh 'date';
				sh 'sh Build.sh'
			}
		
			
			}
		
	}

	
	post {
		always {
			echo 'This will always run'
		}
		success {
			echo 'This will run only if successful'
		}
		failure {
			echo 'This will run only if failed'
		}
		unstable {
			echo 'This will rin only if the run was marked unstable'
		}
		changed {
			echo 'This will run only if the state of the Pipeline has changed'
			echo 'For example, if the Pipeline was previously failing but is now successful'
		}
	}
}

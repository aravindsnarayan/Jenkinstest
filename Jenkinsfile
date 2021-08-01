pipeline {
	agent any
	stages {
		stage('Git-Checkout') {
			steps {
				echo "Checking out from Github Repo";
				sh 'date';
				git branch: 'main', url: 'https://github.com/aravindsnarayan/Jenkinstest.git'
			}
		}
	
		stage('Build') {
			steps {
				echo "Building the checked-out project!";
				sh 'date';
				sh 'sh Build.sh'
			}
		}
	
		stage('Unit-Test') {
			steps {
				echo "Running Unit Tests";
				sh 'date';
				sh 'sh Unit.sh'
			}
		}
	
		stage('Quality Check') {
			steps {
				echo "Verifying Quality Gate";
				sh 'date';
				sh 'sh Quality.sh'
			
			}
		}
	
		stage('Deploy') {
			steps {
				echo "Deploying to Stage Environment";
				sh 'date';
				sh 'sh Deploy.sh'
			
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

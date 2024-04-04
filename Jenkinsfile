pipeline {
	agent any
	stages {
		stage('Git-Checkout') {
			steps {
					echo "Checout form git repo!";
					git branch: 'main', url: 'https://github.com/MaximeMRF/jenkins-script.git'
			}
		}

		stage('Build') {
			steps {
			        sh 'chmod +x script.sh'
					sh './script.sh'
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
			echo 'This will run only if unstable'
		}
		changed {
			echo 'This will run only if the state of the pipeline has changed'
		}
	}
}

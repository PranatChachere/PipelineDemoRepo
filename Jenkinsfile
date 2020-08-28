pipeline
{
	agent {
	    label 'testAgents'
	}
	stages {
		stage('Checkout Stage') {
			steps {
				echo 'Checkout from github repository!'
				// Add commands here
                    git 'https://github.com/PranatChachere/PipelineDemoRepo.git'
			}
		}
    	stage('Build Stage') {
			steps {
				echo 'Built successfully!'
				// Add commands here
				bat label: 'Build File', script: 'Build.bat'
			}
		}
		stage('JUnit Stage') {
			steps {
				echo 'Junit tests passed successfully!'
				// Add commands here
				bat label: 'JUnit File', script: 'JUnit.bat'
				
			}
		}
		stage('Quality Gate Stage') {
			steps {
				echo 'AppScan Quality gate passed successfully!'
				// Add commands here
				bat label: 'QualityGate File', script: 'QualityGate.bat'
				
			}
		}
		stage('Deploy Stage') {
			steps {
				echo 'Deployed successfully!'
				// Add commands here
			    bat label: '', script: 'Deploy.bat'
			}
		}
	}
	post {
		always {
			echo 'This will always run...'
		}
		success {
			echo 'This will run only if the successful...'
		}
		failure {
			echo 'This will run only if the failed...'
		}
		unstable {
			echo 'This will run only if the run was marked as unstable...'
		}
		changed {
			echo 'This will run only of the state of the pipeline is changed...'
		}
	}
}

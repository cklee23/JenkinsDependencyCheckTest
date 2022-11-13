pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '', odcInstallation: 'test1'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}

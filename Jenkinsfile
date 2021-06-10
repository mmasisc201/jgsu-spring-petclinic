pipeline {
	agent any

	stages {
		stage('Build') {
			steps {
				// Run Maven on a Unix agent.
				sh "./mvnw clean package"

				// To run Maven on a Windows agent, use
				// bat "mvn -Dmaven.test.failure.ignore=true clean package"
			}
		}
	}
	post {
		always {
			junit '**/target/surefire-reports/TEST-*.xml'
			archiveArtifacts 'target/*.jar'
		}
	}
}
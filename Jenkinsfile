pipeline {
	agent any
	stages {
		stage("checkout:git") {
			steps {
				git branch: "master", url: "https://github.com/jenkins-docs/simple-java-maven-app"
			}
		}

		stage("Build:Maven") { 	
			steps {
				sh '$MVN -B -DskipTests clean package' 
			}
		}
		
		stage("Analise:Sonar") {
          	  steps {
			sh '$MVN sonar:sonar \
			-Dsonar.projectKey=sample-java-app \
			-Dsonar.host.url=http://34.69.5.32:9000 \
			-Dsonar.login=75e2e81e0354d15c0f6fabc6baab1e7110fcbb6e'
                }
            }
        }
}

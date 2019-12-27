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
			-Dsonar.projectKey=BecaDevOps:master \
			-Dsonar.host.url=http://localhost:9000 \
			-Dsonar.login=4fef96852af3a9a6974492fc678a248141b6a134'
                }
            }
        }
}

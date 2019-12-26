pipeline {

	stage ("checkout:git") {
		git branch: "master", url: "https://github.com/jenkins-docs/simple-java-maven-app"
	}

	stage("Build:Maven") { 
		steps {
			sh 'mvn -B -DskipTests clean package' 
		}
	}
}
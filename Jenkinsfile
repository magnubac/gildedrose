#!/usr/bin/env groov

node {
	
	stage('Build'){
		sh "docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn clean package"
	}

	stage('Deploy'){
		junit **/target/surefire-reports/TEST-*.xml
	}
}

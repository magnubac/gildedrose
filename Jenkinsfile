#!/usr/bin/env groov

node {
	
	stage('Build'){
		sh "mvn clean package"
	}

	stage('Deploy'){
		junit '**/target/surefire-reports/TEST-*.xml'
	}
}

#!/usr/bin/env groovy

node {

	stage('Preparation'){
		sh 'git clone git@github.com:magnubac/gildedrose.git'
	}
	
	stage('Build'){
		sh 'docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install'
	}

	stage('Deploy'){
		junit '**/target/surefire-reports/TEST-*.xml'
		archive 'target/gildedrose-*.jar'
	}
}

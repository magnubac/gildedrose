#!/usr/bin/env groovy

node {

	stage('Preparation'){
		git credentials: '0b245a8f-f5b7-45fe-ad40-360110f071c7', url: 'git@github.com:magnubac/gildedrose.git'
	}
	
	stage('Build'){
		sh 'docker run -i --rm --name my-maven-project -v "$PWD":/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install'
	}

	stage('Deploy'){
		junit '**/target/surefire-reports/TEST-*.xml'
		archive 'target/gildedrose-*.jar'
	}
}

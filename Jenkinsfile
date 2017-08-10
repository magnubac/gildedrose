#!/usr/bin/env groovy

node {
	
	stage('Build'){
		withMaven(
                maven: 'M3',
       	        //mavenSettingsConfig: 'my-maven-settings',
        	//mavenLocalRepo: '.repository') {
			sh "mvn clean package"
		}
	)

	stage('Deploy'){
		junit '**/target/surefire-reports/TEST-*.xml'
	}
}

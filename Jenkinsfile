#!/usr/bin/env groov

node {
	
	stage('Build'){
		build 'gilded rose'
	}

	stage('Deploy'){
		always {
			archive 'target/gildedrose-*.jar'
		}
	}
}

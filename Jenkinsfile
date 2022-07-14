// Powered by Infostretch 

timestamps {

node () {

	stage ('Cash-App Freestyle - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GitHubcredentials2', url: 'https://github.com/dominiondemo/American-Express-UAT']]]) 
	}
	stage ('Cash-App Freestyle - Build') {
 			// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn install " 
			} else { 
 				bat "mvn install " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn sonar:sonar " 
			} else { 
 				bat "mvn sonar:sonar " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.6') { 
 			if(isUnix()) {
 				sh "mvn deploy " 
			} else { 
 				bat "mvn deploy " 
			} 
 		} 
	}
}
}
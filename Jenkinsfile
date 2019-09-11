pipeline {
	agent any
	stages {
	    stage ('Build Stage') {
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			sh 'mvn -f my-app/pom.xml clean compile'
			}
		}
	    }
	    
	    stage ('Test Stage') {
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			sh 'mvn -f my-app/pom.xml test'
			}
		}
	    }
	    stage ('Installation Stage') {
		when {
			branch 'master'
			allOf {
			environment name: 'DEPLOY_TO', value: 'production'
			}
		     }	
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			sh 'mvn -f my-app/pom.xml install'
	         }
	        }
            }
        } 
}

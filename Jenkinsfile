pipeline {
	agent any
	stages {
	    stage ('Build Stage') {
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			mvn clean compile
			}
		}
	    }
	    
	    stage ('Test Stage') {
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			mvn test
			}
		}
	    }
	    stage ('Installation Stage') {
		steps {
			withMaven(maven : 'Maven_3.5.2') {
			mvn install
			}
		}
            }
        } 
}

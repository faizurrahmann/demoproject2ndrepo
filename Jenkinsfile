pipeline {
	agent any
	stages {
	    stage ('Build Stage') {
		steps {
			withMaven(maven : 'maven 3.5.2') {
			sh 'mvn clean compile'
			}
		}
	    }
	    
	    stage ('Test Stage') {
		steps {
			withMaven(maven : 'maven 3.5.2') {
			sh 'mvn test'
			}
		}
	    }
	    stage ('Installation Stage') {
		steps {
			withMaven(maven : 'maven 3.5.2') {
			sh 'mvn install'
			}
		}
            }
        } 
}

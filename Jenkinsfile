pipeline {
	agent any
	stages {
	    stage ('clean up') {
	        steps {
	            cleanWs()
	        }
	    }
	    
	    stage ('clone') {
			steps {
				sh 'git clone https://github.com/rakesh-2502/java-maven-app.git'
			}
	    }
		stage ('build') {
			steps {
			    dir ('java-maven-app'){
				    sh 'mvn clean install -DskipTests'
			    }
			}
		
		}
		stage ('test') {
			steps {
			    dir ('java-maven-app'){
				    sh 'mvn test'
			    }
			}
			
		}
		stage ('run') {
			steps {
			    dir ('java-maven-app'){
			    	sh './scripts/deliver.sh'
			    }
			}
		
		}
	}
}
		
		
	

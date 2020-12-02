pipeline {
    agent any
	tools {
		maven 'Maven'
	}
	
	environment {
		dockerImage =''
		registry = "amit873/test77" 
	        registryCredential = 'dockerhub_id' 
			
	}
	
    stages {
	    stage('Scm Checkout') {
		    steps {
			    checkout scm
		    }
	    }
	    
	    stage('Build') {
		    steps {
			    sh 'mvn clean package'
		    }
	    }
	    
	    
	    
	    stage('Building our image') { 
            	steps { 
                	script { 
                    		dockerImage = docker.build registry + ":$BUILD_NUMBER" 
                	}
            	} 
           }
	    
	    
	   
    }
}

pipeline {
    agent any
	tools {
		maven 'Maven'
	}
	
	environment {
		registry = "amit873/test77" 
	        registryCredential = 'dockerhub_id' 
		PROJECT_ID = 'jenkins-296812'
                CLUSTER_NAME = 'k8s-cluster'
                LOCATION = 'us-central1-c'
                CREDENTIALS_ID = 'KUBERNETES_JSON'		
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

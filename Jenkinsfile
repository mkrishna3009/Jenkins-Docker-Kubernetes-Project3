pipeline {
    agent any
	tools {
		maven 'Maven'
	}
	
	environment {
		PROJECT_ID = 'polar-storm-345016'
                LOCATION = 'us-central1 '
                CREDENTIALS_ID = 'ID'		
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
	    }
	    
	    stage('Test') {
		    steps {
			    echo "Testing..."
			    sh 'mvn test'
		    }
	    }
	    stage('upload artifact') {
                               steps {
                                 sh '"mvn -B clean deploy"
'
                    }
            }

pipeline {
    agent any

    stages {
        stage('Get Latest Sourcecode') {
            steps {
	        git 'https://github.com/ravishsubramanya/Jenkins_multijob_pipeline_code.git'
            }
        }

  	 stage('Compile') {
         	steps {
                bat 'mvn clean compile'
            }
        }
    	    
        stage('Test') {
            steps {
		input message: 'Are you sure to proceed to next step? ', ok: 'Yes'
               bat "mvn test"
            }
        }
	stage('Build'){
	    steps {
	      input message: 'Do you want to continue deployement to UAT ?', ok: 'Yes'
	     bat "mvn clean compile package"
	     }
	    }
	  
    }
}

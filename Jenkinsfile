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
                 sh "mvn clean compile"
            }
        }
        stage('Test') {
            steps {
		input message: 'Are you sure to proceed to next step? ', ok: 'Yes'
               sh "mvn test"
            }
        }
	    stage('Build'){
	      input 'Do you want to continue deployement to UAT ?' , ok: 'Yes'
	     sh "mvn clean compile package"
	    }
	    
    }
}

pipeline {
    agent any

    stages {
        stage('Get Latest Sourcecode') {
            steps {
	        git 'https://github.com/ravishsubramanya/Jenkins_multijob_pipeline_code.git'
            }
        }
     steps {
            withMaven(maven : 'apache-maven-3.9.6') {
                bat'mvn clean compile'
            }
        }
    }
        stage('Test') {
            steps {
		input message: 'Are you sure to proceed to next step? ', ok: 'Yes'
               sh "mvn test"
            }
        }
	stage('Build'){
	    steps {
	      input message: 'Do you want to continue deployement to UAT ?', ok: 'Yes'
	     sh "mvn clean compile package"
	     }
	    }
	  
    }
}

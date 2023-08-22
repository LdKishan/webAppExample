pipeline{
	agent any
tools{
	maven 'local_maven'
}
	
	stages{

	stage('SCM Checkout'){

	steps{
	git branch: 'master', url: 'https://github.com/LdKishan/webAppExample.git'
	}
	} 
stage('Build'){

	steps{
	sh 'mvn clean package'
	}
	} 
stage ('Deploy to Tomcat Server'){
			steps{
				deploy adapters: [tomcat9(credentialsId: 'abd0586d-0f34-4d69-bc82-b1b9194bc521', path: '', url: 'http://54.175.134.91:9090/')], contextPath: 'webAppExample', war: '**/*.war'
			}

		}
	
	}
	}

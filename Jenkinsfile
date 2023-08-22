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
				deploy adapters: [tomcat9(credentialsId: 'tomi', path: '', url: 'http://54.175.134.91:9090/')], contextPath: 'Webappexample', war: '**/*.war'
			}

		}
	
	}
	}

pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('a'){
			steps{
				git branch:'master', url:'https://github.com/rishitabafna/MyWebApp.git'
			}
		}
		stage('b'){
			steps{
				sh 'mvn clean package'
			}
		}
		
	}
}

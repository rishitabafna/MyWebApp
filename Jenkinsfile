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
		stage('c'){
			steps{
				archiveArtifacts artifacts:'target/*.war', fingerprint:true
			}
		}
		stage('d'){
			steps{
				sh 'mvn clean package',
				ansiblePlaybook playbook: 'deploy.yml', inventory:'hosts.ini'				
			}
		}
	}
}

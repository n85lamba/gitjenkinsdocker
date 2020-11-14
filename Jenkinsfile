pipeline{
	agent any
	tools{
		maven 'm3'
		jdk 'jdk8'
	}
	stages{
		stage('Checkout') {
			steps {
				//checkout scm
				git'https://github.com/n85lamba/gitjenkinsdocker.git'
			}
		}
		stage('Compile') {
			steps {
				sh 'mvn clean compile'
			}
		}
        stage('Test') {
			steps {
				sh 'mvn clean test'
			}
		}
        stage('Package') {
			steps {
				sh 'mvn clean package'
			}
		}
        stage('ArchiveArtifact') {
			steps {
				archiveArtifact 'target/*.jar'
			}
		}
        
	}
}	

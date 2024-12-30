pipeline {
	agent any
	
	stages {
		stage('Buld jar') {
			bat "mvn clean package -DskipTests"
		}
		stage('create image') {
			bat "docker build -t=devshringi/selenium ."
		}
		stage('push image') {
			bat "docker push devshringi/selenium"
		}
	}
}
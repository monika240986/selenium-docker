pipeline {
	agent any

	stages {
		stage('Buld jar') {
		    steps {
		         bat "mvn clean package -DskipTests"
		    }
		}
		stage('create image') {
            steps {
                 bat "docker build -t=devshringi/selenium ."
            }
		}
		stage('push image') {
            steps {
                 bat "docker push devshringi/selenium"
            }
		}
	}
}
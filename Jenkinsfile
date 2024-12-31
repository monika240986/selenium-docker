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
            environment {
                DOCKER_HUB = credentials('docker')
            }
            steps {
                 bat 'docker login -u ${DOCKER_HUB_USR} -p ${DOCKER_HUB_PSW}'
                 bat "docker push devshringi/selenium"
            }
		}
	}
	post {
	    always {
	        bat "docker logout"
	    }
	}
}
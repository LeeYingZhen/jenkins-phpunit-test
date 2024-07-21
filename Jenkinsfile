pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
        environment {
        	DOCKER_HOST = 'npipe:////./pipe/docker_engine'
        }
	stages {
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}
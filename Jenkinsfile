#!groovy

pipeline {
	agent none
  stages {
  	stage('Maven Install') {
    	agent any
      steps {
      	sh 'mvn clean install'
      }
    }
    stage('Docker Build') {
    	agent any
      steps {
        sh 'export DOCKER_TLS_VERIFY=1'

      	sh 'docker build --tlscacert=/docker-certs/ca.pem --tlscert=/docker-certs/server-key.pem --tlskey=/docker-certs/server-key.pem -t shanem/spring-petclinic:latest .'
      }
    }
  }
}
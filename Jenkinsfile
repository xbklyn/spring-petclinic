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

        sh 'export DOCKER_CERT_PATH=/docker-certs/ca.pem'

      	sh 'docker build -t shanem/spring-petclinic:latest .'
      }
    }
  }
}
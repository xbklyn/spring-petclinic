#!groovy
pipeline {
	agent any
  stages {
  	stage('Maven Install') {
    	agent any
      steps {
      	sh 'mvn clean install'
      }
    }
  }
}
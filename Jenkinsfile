#!groovy

pipeline {
  agent none
  stages {
      stage('Cloning our Git') {
      steps {
	git 'https://github.com/ismailyenigul/hacicenkins.git'
	}
	}
        stage('python Install') {
    	agent {
      	docker none {
           image 'python:3.8-alpine'
        }
      }
      steps {
      	sh 'python --version'
      }
    }
    stage('Docker Build') {
    	agent any
        steps {
      	sh 'docker build -t pooja34114/dockertest:latest .'
      }
}
//  stage('Docker Push') {
//     agent any
//       steps {
//       	withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
//           sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
//           sh 'docker push pooja34114/dockertest:latest'
//         }
//       }
//     }
  }
}

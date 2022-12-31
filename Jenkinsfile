pipeline { 
  agent {
  
  stages {
    stage ('Git checkout') { 
	steps {
          git url: 'https://github.com/pooja34114/dockertest.git', credentialsId: 'git-credentials', branch: 'master'
	 }
	}
    stage ('python Install') {
    agent {
      docker {
        image 'python:3.8-alpine'
     }
    }
      steps {
      	sh 'python --version'
      }
    }
    stage ('Docker Build') {
    agent {
      steps {
      	sh 'docker build -t pooja34114/dockertest:latest .'
      }
}
  }
}
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
 


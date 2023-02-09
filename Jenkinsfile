pipeline {
    // ① Select a Jenkins slave with Docker capabilities
    agent any
environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub')
  }
    stages {

	 //Build a container with the code source of the application
        stage('Build') {
            steps {
                sh "docker build . -t rajindersingh1/hellopython:latest"
            }
        }
stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin '
      }
    }

	// Run the test using the built docker image
        stage('Push') {
            steps {
                script {
                    sh "docker push rajindersingh1/hellopython:latest"
                }
            }
        }
    }
 }

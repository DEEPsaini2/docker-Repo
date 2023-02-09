pipeline {
    // ① Select a Jenkins slave with Docker capabilities
    agent any
    stages {

	 //Build a container with the code source of the application
        stage('Build') {
            steps {
                sh "docker build . -t hellopython:latest"
            }
        }

	// Run the test using the built docker image
        stage('Push') {
            steps {
                script {
                    sh "docker push hellopython:latest"
                }
            }
        }
    }
 }

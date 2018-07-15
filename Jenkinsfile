pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
			    sh 'sudo docker build -t myapp2:latest .'
                sh 'sudo docker images'
                script {
                  docker.withRegistry('https://635019503179.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:demo-ecr-credentials') 
				  {
                   docker.image('hello-world').push('latest')
                  }
            }
        }
		}
		stage('Deploy') {
		    steps {
			    sh 'kubectl create -f eks-Deployment.yml'
				sh 'kubectl create -f eks-Service.yml'
				sh 'kubectl get services -o wide'
				sh 'kubectl get pods'
            }
        }
        }
}

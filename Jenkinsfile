pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'sudo docker build -t myapp2 .'
            }
        }
        stage('Deploy') {
           docker.withRegistry('https://635019503179.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:demo-ecr-credentials') {
             docker.image('myapp2').push('latest')
            steps {
                echo 'Build successfull'
            }
        }
        }
    }
}

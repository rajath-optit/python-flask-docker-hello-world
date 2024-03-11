pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'master',
                        credentialsId: 'rajath-my-git-pat',
                        url: 'https://github.com/rajath-optit/python-flask-docker-hello-world.git'
                    echo "Checked out Git repository"
                }
            }
        }

        stage('Build with python') {
            steps {
                script {
                    // Assuming your Gradle wrapper is in the root directory of your repository
                    sh './app.py' // Command to execute Gradle build
                }
            }
	}
}
}

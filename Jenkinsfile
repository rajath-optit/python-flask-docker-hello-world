pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'test_python',
                        credentialsId: 'rajath-my-git-pat',
                        url: 'https://github.com/rajath-optit/flask-hello-world-devops-project.git'
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

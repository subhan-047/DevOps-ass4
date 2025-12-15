pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/subhan-047/DevOps-ass4.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Build Successful'
            }
        }

        stage('Test') {
            steps {
                echo 'No Tests Implemented'
            }
        }

        stage('Deploy to EC2') {
            steps {
                sshagent(['ec2-key']) {
                    sh """
                    scp -o StrictHostKeyChecking=no index.html ubuntu@16.16.182.179:/var/www/html/index.html
                    """
                }
            }
        }
    }
}

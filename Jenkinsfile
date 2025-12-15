pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git 'https://github.com/YOUR-USERNAME/azure-jenkins-ci-cd.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build required for static HTML application'
            }
        }

        stage('Test') {
            steps {
                echo 'No tests configured'
            }
        }

        stage('Deploy to Azure VM') {
            steps {
                sshagent(['azure-vm-credentials']) {
                    sh '''
                    scp -o StrictHostKeyChecking=no index.html azureuser@AZURE_PUBLIC_IP:/var/www/html/
                    ssh azureuser@AZURE_PUBLIC_IP sudo systemctl restart nginx
                    '''
                }
            }
        }
    }
}

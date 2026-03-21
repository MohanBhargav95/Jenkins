pipeline {
    agent any
    environment{
        Project= "Jenkins"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh"""
                       echo 'Building application...'
                       echo $Project
                    """
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh"""
                       echo 'Testing application...'
                    """
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh"""
                       echo 'deploying application...'
                    """
                }
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline finished.'
            cleanWs() 
        }
        success {
            echo 'Success! Sending notification...'
        }
        failure {
            echo 'Failed. Check the logs.'
        }
    }
}

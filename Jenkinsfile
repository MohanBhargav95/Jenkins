pipeline {
    agent any
    environment{
        My_Project= "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh"""
                       echo 'Building application...'
                       echo $My_Project
                       sleep 12
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

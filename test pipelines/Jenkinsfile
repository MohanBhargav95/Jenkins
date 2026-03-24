pipeline {
    agent any
    environment{
        My_Project= "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage('Build') {
            steps {
                script {
                    sh"""
                       echo 'Building application...'
                       echo $My_Project
                       echo "Hello ${params.PERSON}"
                       echo "Biography: ${params.BIOGRAPHY}"
                       echo "Toggle: ${params.TOGGLE}"
                       echo "Choice: ${params.CHOICE}"
                       echo "Password: ${params.PASSWORD}"
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

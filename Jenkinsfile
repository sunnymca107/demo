pipeline {
    agent any // Runs on any available agent

    stages {
        stage('Build') {
            steps {
                echo 'Compiling source code...'
                sh 'make' // Execute shell command
            }
        }
        stage('Test') {
            steps {
                echo 'Running unit tests...'
                sh 'make check'
                junit 'reports/**/*.xml' // Archive test results
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to production...'
                sh 'make publish'
            }
        }
    }
    
    post {
        always {
            echo 'I will always run, regardless of success or failure!'
        }
    }
}

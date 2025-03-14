pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Shrujanapatil/Shrujanapatil_PES1UG22CS587_Jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                build 'PES1UG22CS587-1'
                sh 'g++ ./hello.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}

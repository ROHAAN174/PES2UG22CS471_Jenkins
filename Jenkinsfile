pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/ROHAAN174/PES2UG22CS471_Jenkins.git']]
                ]) 
            }
        }

        stage('Build') {
            steps {
                //error 
                //sh 'g main/hllo.cpp -o main/output'
                sh 'g++ main/hello.cpp -o main/output'
            }
        }

        stage('Test') {
            steps {
                sh './main/output'
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

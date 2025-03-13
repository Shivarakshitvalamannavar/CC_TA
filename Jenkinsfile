pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Shivarakshitvalamannavar/CC_TA.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG22CS562-1'
                sh 'g++ ./main/hello1.cpp'
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

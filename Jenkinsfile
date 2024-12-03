pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                echo 'Without docker'
                sh '''
                
                ls -la
                touch container-no.txt
                '''
                
            }
        }
        
        stage('w/ docker') {
            agent {
                docker {
                image 'node:18-alpine'
                reuseNode true
                }
            }
            steps{
                echo 'With docker'
                sh '''
                npm --version
                ls -la
                touch container-yes.txt
                '''
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Without Docker') {
            steps {
                sh '''
                echo "Without Doclker"
                touch t2.txt
                ls -al
                '''
            }
        }
        stage('With Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "With docker"
                ls -al
                touch t3.txt
                
                '''
                sh 'npm --version'
            }
        }
    }
}

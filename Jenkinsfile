/*pipeline {
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
*/
pipeline{
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh 'echo "Hello World"'
                sh '''
                    ls -al
                    node --version
                    npm --version
                    npm ci # this will install the CI-CD Pipleine software
                    npm run build #this will run the build
                    ls -al


                '''
            }
        }
    }
}
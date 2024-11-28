pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
                    echo "Without docker"
                    touch container-no.txt
                    ls -la
                '''
                    
            }
        }
        stage('w/ docker') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "With docker"
                npm --version
                touch container-yes.txt
                ls -la
            '''
            }
        }
    }
}
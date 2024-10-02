pipeline {
    agent any

    stages {
        stage('without docker') {
            steps {
                echo 'Hello World'
            }
        }
    
         stage('With docker') {
                agent{
                        docker{
                            image 'node:18-alpine'
                        }
                }
                steps {
                    
                    sh 'echo "Hello World after docker"'
                    sh 'npm --version'
                }
            }
    }
}
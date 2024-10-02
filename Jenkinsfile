pipeline {
    agent any
    stages {
        stage('without docker') {
            steps {
                echo 'Hello World'
                sh '''
                
                touch withoutdocker.txt
                
                '''
            }
        }
    
         stage('With docker') {
                agent{
                        docker{
                            image 'node:18-alpine'
                            reuseNode true
                        }
                }
                steps {
                    sh '''
                    
                     echo "Hello World after docker"
                     npm --version
                     touch withdoc.txt                
                '''
                }
            }
    }
}
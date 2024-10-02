pipeline {
    agent any
    stages {
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
       	  stage('Build')
       	  {
       	  	agent{
                        docker{
                            image 'node:18-alpine'
                            reuseNode true
                        }
                }
       	  	steps {
       	  				sh '''
       	  				 echo "Running the build"
               		      npm run build
               		      grep "build" *
                     
                     '''
       	  		}
       	  		
       	  	}
       	  	
       	  	stage('Test')
       	  	{
       	  	steps{
       	  	
       	  		sh '''
       	  		
       	  		echo "In the test stage"
			       		echo "Have to find the file index.html inside the build folder"
       					grep "index.html" "*/build"
       					npm test
       	  		
       	  		'''
       	  	}
       	  }
	    }
}
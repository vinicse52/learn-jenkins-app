pipeline {
    agent any
    stages {
              
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
       	  				 ls -la
       	  				 npm ci
               		     npm run build
               		     grep "build" *
               		     
               		     ls -la
                     
                     '''
       	  		}
       	  		
       	  	}
       	  	
       	  	stage('Test')
       	  	{
       	  		agent{
                        docker{
                            image 'node:18-alpine'
                            reuseNode true
                        }
                }
       	  	steps{
       	  	
       	  		sh '''
       	  		
       	  		echo "In the test stage"
			       		echo "Have to find the file index.html inside the build folder"
       					grep "index.html" "build"
       					npm test
       	  		
       	  		'''
       	  	}
       	  }
	    }
}
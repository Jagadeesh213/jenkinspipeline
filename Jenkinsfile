pipeline {
    agent any
    stages {
        stage('build') {
                steps {
                        echo 'Running the build...'
			
                }
        }
	    stage('test: integration-&-quality'){
		    
		steps {
			echo 'Running the integration and quality test...'
        }
	    }
        stage('test: functional') {
                
                steps {
			echo "Running the functional test..."
                        }
        }
        stage('test: load-&-security') {
                parallel {
                        stage('performance Test') {
                                steps{
                                        echo "Running the performance test..."
                                }
                        }
                        stage('Integration test') {
                        
				steps {
					echo 'Running the integration test..'
				}
                               
			}  }
        }
        stage('approval') {
                
                steps {
			echo "Running the approval process"
                        }
        }
        stage('deploy:prod') {
                
                steps {
     			echo "Running the deployment in prod process"
                        }
     }
 // stage('Deploy to Tomcat') {
 //     steps {
        // Deploy your application (e.g., Docker, Kubernetes)
 //        sh sshagent(credentials: ['27b86657-ba75-4b78-9ad6-8a9146bfbb3a']) {
 //                   sh 'ssh root@tomcat-server "sudo systemctl stop tomcat"'
 //                   sh 'ssh root@tomcat-server "rm -rf /opt/tomcat/webapps"'
 //                   sh 'scp /var/lib/jenkins/workspace/SAMPLE/target/webapp/webapp.war root@tomcat-server:/opt/tomcat/webapps'
 //                   sh 'ssh root@tomcat-server "sudo systemctl start tomcat"'
 //                   ssh -o StrictHostKeyChecking=no host

   //   }
  //  }	
  //      }
    }
}

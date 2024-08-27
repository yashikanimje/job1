pipeline{
      agent any
	parameters {
	  choice choices: ['DEV', 'QA', 'UAT'], description: 'This is a choice Parameter', name: 'ENVIRONMENT'
	}
    
            stages{
                  stage(checkout){
                        steps{
                            checkout scm
                              }
                        }
               stage(build){
                     steps{
                       sh 'mvn install'
                        }
                       }
                  stage(Deployment){
                        steps{
                              script {
			 if ( "${env.ENVIRONMENT}" == 'QA' ){
        	sh 'cp target/job1.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
        	echo "deployment has been done on QA!"
			 }
			elif ( "${env.ENVIRONMENT}" == 'UAT' ){
    		sh 'cp target/job1.war /home/yashika/Documents/devtool/apache-tomcat-9.0.93/webapps'
    		echo "deployment has been done on UAT!"
			}
			echo "deployment has been done!"
			fi
                        }
                  }
    }
}

